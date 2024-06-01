# Desafio de Transição de Frota

**Introdução**

Bem-vindo à quinta edição do Hackathon Shell.ai para Energia Sustentável e Acessível. O Hackathon Shell.ai reúne mentes brilhantes apaixonadas por soluções digitais e IA, para enfrentar desafios energéticos reais e ajudar a construir um mundo de baixo carbono onde todos podem acessar e pagar pela energia. Nas quatro edições anteriores, abordamos alguns dos desafios digitais em torno da transição energética: otimização de layout de parques eólicos (2020), previsão de irradiância para geração de energia solar (2021), posicionamento ideal de estações de carregamento de veículos elétricos (EV) (2022) e otimização da cadeia de suprimentos para biorefinarias (2023). Este ano, focamos na descarbonização de frotas - um problema de transição no setor de mobilidade.

**Desafio**

Frotas profissionais, de entrega e operacionais são uma contribuição significativa para as emissões globais de gases de efeito estufa. Os proprietários de frotas aspiram a alcançar emissões líquidas zero prontamente; no entanto, a transição apresenta um dilema complexo. Equilibrar a urgência de alcançar emissões líquidas zero com a sustentabilidade dos negócios e a satisfação do cliente requer uma estrutura de tomada de decisão que considere fatores como tempo, localização e abordagem. Neste hackathon, você terá a chance de desenvolver modelos matemáticos para otimizar estratégias de descarbonização de frotas, para ajudar os proprietários de frotas a tomar decisões informadas que se alinhem com seus objetivos de transição energética e resultados de negócios. Ao aproveitar o poder dos dados e dos modelos matemáticos, você navegará pelas complexidades das previsões de demanda, dissecará perfis de emissão e encontrará maneiras de atingir metas de emissão ambiciosas. O objetivo final é desenvolver soluções engenhosas que equilibrem a eficácia operacional e o impacto ambiental.

**Declaração do Problema**

O transporte rodoviário é a espinha dorsal da cadeia de suprimentos, desempenhando um papel fundamental no transporte de mercadorias e no fortalecimento da economia. Este modo de transporte tem vantagens como flexibilidade, serviço porta a porta e conectividade entre cidades, vilas e aldeias. Embora venha com conveniência e vantagem, as frotas profissionais, de entrega e operacionais são uma contribuição significativa para as emissões globais de gases de efeito estufa. Os proprietários de frotas aspiram a alcançar emissões líquidas zero prontamente; no entanto, a transição apresenta um dilema complexo. Equilibrar a urgência de alcançar emissões líquidas zero com a sustentabilidade dos negócios e a satisfação do cliente requer uma estrutura de tomada de decisão que considere fatores como tempo, localização e abordagem. Neste hackathon, você terá a chance de desenvolver modelos matemáticos para otimizar estratégias de descarbonização de frotas, para ajudar os proprietários de frotas a tomar decisões informadas que se alinhem com seus objetivos de transição energética e resultados de negócios. Ao aproveitar o poder dos dados e dos modelos matemáticos, você navegará pelas complexidades das previsões de demanda, dissecará perfis de emissão e encontrará maneiras de atingir metas de emissão ambiciosas. O objetivo final é desenvolver soluções engenhosas que equilibrem a eficácia operacional e o impacto ambiental. Forneceremos vários dados de ‘demanda’ anuais de um operador de frota que devem ser atendidos. Os dados de demanda são ainda divididos em vários caçambas de tamanho e distância que indicam quais tamanhos de veículo devem ser usados e quanto de distância por dia eles podem percorrer. Estas são algumas restrições adicionais impostas para atender à demanda do cliente. Fornecemos vários veículos dos seguintes 3 trens de força: Diesel, GNL e BEV (Veículo Elétrico a Bateria). Para cada um desses veículos, o custo, a faixa operacional anual, o caçamba de distância que eles podem cobrir e o ID do veículo (identificador único que ajuda você a referenciá-los em sua solução) são fornecidos. Incluímos as informações sobre o consumo de combustível de cada modelo do veículo e os tipos de combustível correspondentes. Além disso, também incluímos o custo de cada tipo de combustível, juntamente com a quantidade de emissões de carbono por cada um deles, para cada ano. Finalmente, você também é fornecido com os limites totais de emissão de carbono que não devem ser excedidos a cada ano. Todos os dados fornecidos abrangem os anos de 2023 a 2038 (ambos os anos inclusive), para um total de 16 anos

Sua solução deve fornecer uma composição de frota ideal ao longo dos anos, que atenda a toda a demanda da cadeia de suprimentos e restrições, enquanto respeita os limites de emissão de carbono para cada ano e tem o menor custo total possível. Os dados fornecidos a você e a solução esperada de você foram explicados com mais detalhes na próxima seção.

**Descrição dos dados**

O conjunto de dados contém o seguinte:

- **demand.csv**: Este arquivo fornece a demanda total de distância anual (em kms) que precisa ser satisfeita com veículos do tamanho Sx (caçamba de tamanho) que podem percorrer pelo menos um mínimo de Dx (caçamba de distância) por dia. Por exemplo, a linha 1 indica que há uma demanda anual de 869181 km para os veículos de tamanho S1 que podem percorrer pelo menos um mínimo de caçamba de distância D1 por dia.
- **vehicles.csv**: Este arquivo fornece o ID do veículo (modelo), tipo de veículo (trem de força), caçamba de tamanho, ano em que você pode comprá-lo, custo de compra, alcance anual (em kms) e o caçamba de distância máxima diária que pode percorrer.
- **vehicles_fuels.csv**: Este arquivo fornece o consumo de combustível (unidade de combustível consumida/km) para cada ID de veículo usando um determinado tipo de combustível.
- **fuels.csv**: Existem 5 tipos de combustível e, para cada um, esta tabela fornece a emissão de carbono por unidade de combustível e o custo (mediano) por unidade de combustível ao longo de todos os anos. Também inclui a incerteza no custo do combustível.
- **carbon_emissions.csv**: Fornece os limites totais de emissões de carbono que não devem ser violados para cada ano. É um perfil decrescente ao longo dos anos.
- **sample_submission.csv**: Fornece formato de amostra para envio

As colunas fornecidas no conjunto de dados são as seguintes:

| Nome da coluna | Descrição |
| --- | --- |
| year | 2018, 2019, 20182019 |
| data_type | depot_location, refinery_location, biomass_forecast, biomass_demand_supply, pellet_demand_supply |
| source_index | De 0 a 2417 |
| destination_index | De 0 a 2417 |
| value | Qualquer valor seguindo as restrições do problema |

**Notações**

![Notações](https://he-s3.s3.amazonaws.com/media/uploads/da684fa5-3f31-447e-a544-14cfd8f0dc51.png)

Claro, aqui estão as legendas das equações reescritas em LaTeX:

$$ C_{total} = \text{Custo total de propriedade e operação da frota ao longo de todos os anos.} $$

$$ C_{ins}^y = \text{Custo total do seguro incorrido nos veículos da frota para o ano } y. $$

$$ C_{mnt}^y = \text{Custo total de manutenção incorrido nos veículos da frota para o ano } y. $$

$$ C_{fuel}^y = \text{Custo total de combustível ao queimar algum tipo de combustível } f \text{ em aquecimento no ano } y. $$

$$ V_{srt}^y = \text{Quantia recebida pela venda de alguns veículos da frota no ano } y. $$

$$ V_{cst}^y = S_y - E_y + I_y - O_y + P_y - N_y $$

$$ S_y = \text{Conjunto de todos os veículos na frota operacional no ano } y. $$

$$ E_y = \text{Número de veículos vendidos que foram comprados antes do início do ano } y. $$

$$ I_y = \text{Frota de veículos em uso ou comprados durante aquele ano.} $$

$$ O_y= \text{Número de veículos vendidos que foram comprados antes do início do ano } y. $$

$$ N_{p,y}= F_p + R_p + W_p \text{ (onde } p \text{ indica compra)} $$

$$ N_{s,y}= F_s + R_s + W_s \text{ (onde } s \text{ indica venda)} $$

$$ I_{p,y}= \text{Número de veículos em operação no ano } y \text{ que foram comprados é no ano } p+y'. \text{ (onde } p+y' \text{ indica compra)} $$

$$ O_{s,y}= \text{Custo do seguro que o veículo do ano } s' \text{ incorreu durante o ano } p+y'. \text{ (onde } s'+y' \text{ indica venda)} $$

$$ M^{p'}_y= \text{Custo de manutenção no ano } y \text{ para veículo Y_subj comprado no ano } yp'. \text{ (onde } yp' \text{ indica compra)} $$

$$ M^{s'}_yr= \text{Custo de depreciação no ano } y \text{ para veículo Y_subj vendido no ano } ys'. \text{ (onde } ys' \text{ indica venda)} $$

**Objetivo**

$$ C_{total} = \sum^{2038}_{Y=2023} C^{yr}_{buy} + C^{yr}_{ins} + C^{yr}_{mnt} + C^{yr}_{fuel} - C^{yr}_{sell} $$

$$
C^{BY}_{Y} = \frac{\sum_{VP,YR}(C_{VP,YR}) \cdot N_{VP,YR}}{\sum_{VP,YR}(N_{VP,YR})}
$$

$$
C^{INS}_{Y} = \frac{\sum_{FV,YR}(I^*VRP) \cdot N^*VRP}{\sum_{FV,YR}(N^*VRP)}
$$

$$
C^{MT}_{Y}= \frac{\sum_{FV,YR}(D^*SF) \cdot (N^*mf - mf_k) + C^{IR}}{\sum_{FV,YR}(D^*SF)}
$$

$$
C^{FUEL}_{Y}= \frac{\sum_{VP,FV,YR}(D^*VRP \cdot N^*_f/eff)}{\sum_{VP,FV,YR}(D^*VRP)}
$$

![Objetivo](https://he-s3.s3.amazonaws.com/media/uploads/6d5a0bfd-1dab-4f77-b3e2-9400cadd09d4.png)

**Restrições**

- O veículo do tamanho Sx só pode atender à demanda do caçamba de tamanho Sx.
- O veículo pertencente ao caçamba de distância Dx pode satisfazer todas as demandas para o caçamba de distância D1 a Dx. Por exemplo, o veículo pertencente ao caçamba de distância D4 pode satisfazer a demanda dos caçambas D1, D2, D3, D4; da mesma forma, D3 pode satisfazer D1, D2, D3, mas NÃO D4.
- A emissão total de carbono pelas operações da frota a cada ano deve estar dentro dos limites de emissões de carbono do respectivo ano fornecidos em carbon_emissions.csv. As emissões totais de carbono para um ano são calculadas usando:

![Emissões totais de carbono](https://he-s3.s3.amazonaws.com/media/uploads/c9a8dd89-e5be-4481-b37d-7ee6d082a5c0.png)

- A demanda total anual para cada ano deve ser satisfeita para cada caçamba de distância e tamanho.
- O modelo de veículo do ano 20xx só pode ser comprado no ano 20xx. Por exemplo, Diesel_S1_2026 só pode ser comprado em 2026 e não em nenhum ano subsequente ou anterior.
- Todo veículo tem uma vida útil de 10 anos e deve ser vendido no final do 10º ano. Por exemplo, um veículo comprado em 2025 deve ser vendido no final de 2034.
- Você não pode comprar/vender um veículo no meio do ano. Todas as operações de compra acontecem no início do ano e todas as operações de venda acontecem no final do ano.
- A cada ano, no máximo 20% dos veículos da frota existente podem ser vendidos.

**Avaliação**

Haverá 2 rodadas de avaliação que são as seguintes:

- Público
- Privado

A pontuação gerada para a rodada pública será visível no leaderboard até o final da primeira rodada.

Você deve fornecer a solução em um arquivo .csv. Os nomes das colunas que devem existir no .csv, juntamente com as “entradas válidas”, são fornecidos na tabela abaixo.

| Colunas | Entradas válidas |
| --- | --- |
| Ano | 2023, 2024, ...., 2038 |
| ID | Deve estar entre a lista de IDs fornecida em vehicles.csv |
| Num_Vehicles | >=1 |
| Tipo | Deve estar entre “Buy”, “Use”, “Sell”. |
| Combustível | Deve estar entre “Electricity”, “B20”, “LNG”, “BioLNG”, “HVO”. |
| Distance_bucket | Deve estar entre D1, D2, D3, D4. |
| Distance_per_vehicle(km) | Deve ser >= 0 e <= Alcance anual desse modelo. |

Nota: O caçamba de distância do arquivo de solução corresponde ao caçamba de distância no arquivo demand.csv. Note que este não é o caçamba de distância do próprio veículo (obtemos isso de vehicles.csv de qualquer maneira usando o ID fornecido).

**Informações adicionais**

- O valor de revenda do veículo, o custo do seguro e os custos de manutenção como uma porcentagem de seu custo de compra são fornecidos abaixo para cada ano após a compra do veículo.

![Valor de revenda do veículo, custo do seguro e custos de manutenção](https://he-s3.s3.amazonaws.com/media/uploads/c2bac1dc-565c-4447-8d26-c927e264dc81.png)

Para ilustrar os cálculos, vamos pegar um exemplo de custo de compra = $100 para um veículo comprado em 1º de janeiro de 2025. Usando as porcentagens na tabela acima, os valores podem ser calculados da seguinte maneira:

![Cálculo de valores](https://he-s3.s3.amazonaws.com/media/uploads/646ae323-3ed5-4b65-8aff-43022858ae22.png)

- Mapeamentos de caçamba de distância -

![Mapeamentos de caçamba de distância](https://he-s3.s3.amazonaws.com/media/uploads/bc8a84d0-2a77-42b5-a129-ba82971dfeea.png)

- Mapeamentos de caçamba de tamanho de veículo -

![Mapeamentos de caçamba de tamanho de veículo](https://he-s3.s3.amazonaws.com/media/uploads/b77e8680-f0b2-4c07-a29b-c86db7e39149.png)

Por favor, note que os custos de seguro e manutenção devem ser calculados para todos os veículos da frota (independentemente de serem usados em um determinado ano), enquanto os custos de combustível são apenas para aqueles veículos que serão usados (dirigidos) naquele ano.

**Pontuação**

Se a sua solução satisfizer todas as restrições, primeiro calcularemos o custo total de propriedade e operações da frota da sua solução usando a função de custo geral. Seu custo (quanto menor, melhor) será então convertido em uma pontuação (quanto maior, melhor) entre 30 a 100 usando a seguinte função de transformação para a classificação do leaderboard:

$$
\text{pontuação do leaderboard} = \max\left[30, \left(100 - 70 \times \frac{\text{custo}}{\text{custo de referência}}\right)\right]
$$

Pontuações entre 0 a 26 são reservadas para os códigos de erro detalhados abaixo.

Como você pode ver no arquivo fuels.csv, um custo de combustível mediano junto com uma banda de incerteza foi fornecido. O custo final (que também incluirá os custos de combustível) será um agregado estatístico de 1000 amostras aleatoriamente sorteadas da distribuição de combustível fornecida. O leaderboard público é mostrado para você durante toda a duração da competição. Aqui, você será avaliado até o ano de 2028. O leaderboard privado não será mostrado para você e só será revelado no final da competição. Isso é avaliado para o curso completo de 16 anos de 2023 a 2038. O custo de referência para o leaderboard privado é 172.000.000, e para o leaderboard público é 65.000.000.

**Nota: Pontuações de erro** se o candidato obtiver qualquer pontuação inteira entre 0-26, significa que ele encontrou um erro durante a avaliação.

- **0** Qualquer código de erro não contabilizado
- **1** A entrada do ano deve ser do tipo inteiro.
- **2** A entrada do ID deve ser uma string.
- **3** A entrada Num_Vehicles deve ser do tipo inteiro.
- **4** A entrada do tipo deve ser uma string.
- **5** A entrada de combustível deve ser uma string.
- **6** A entrada do caçamba de distância deve ser uma string.
- **7** A entrada Distance_driven_per_vehicle(km) deve ser do tipo float.
- **8** A entrada do ano deve ser >=2023 e <=2038.
- **9** O ID deve estar na lista fornecida de IDs de veículos.
- **10** Num_Vehicles deve ser > 0.
- **11** O tipo deve assumir valores entre “Buy”, “Sell”, “Use”.
- **12** O combustível deve estar entre “Electricity”, “LNG”, “BioLNG”, “HVO”, “B20”.
- **13** O caçamba de distância deve estar entre “D1”, “D2”, “D3”, “D4”.
- **14** A distância percorrida deve ser >= 0 e <= Alcance anual para aquele modelo.
- **15** Violações da Restrição 2.
- **16** Violação da Restrição 5. O veículo comprado no ano YYYY deve ter YYYY em seu ID.
- **17** Violação da Restrição 6. O veículo comprado em YYYY só pode ser usado por 10 anos.
- **18** Demand.csv tem a demanda referente a 16 combinações (S1_D1, S1_D2, ..., S4_D4) para cada ano. Seu arquivo solution.csv também deve ter todas essas combinações presentes.
- **19** Violação da Restrição 4. Por exemplo, em demand.csv para o ano de 2023 a demanda S1_D1 é de 869181 km. Nas soluções que você fornece, a soma de toda a distância percorrida no ano de 2023 por veículos do tamanho S1 que satisfazem a demanda de distância D1 deve ser >= 869181 km
- **20** Você deve usar o tipo certo de combustível para um determinado veículo.
- **21** Violação da Restrição 8. Você deve vender apenas no máximo 20% da frota a cada ano e nada mais.
- **22** Você só pode "Usar" IDs de veículos que você tem na frota.
- **23** Você só pode "Usar" tantos veículos quantos você tem na frota para cada ID.
- **24** Você só pode "Vender" IDs de veículos que você tem na frota.
- **25** Você só pode "Vender" tantos veículos quantos você tem na frota para cada ID.
- **26** Violação da Restrição 3. A emissão total de carbono pelas operações da frota <= Orçamento de carbono para aquele ano.

*Você não precisa enviar seus arquivos de código-fonte. Quando você enviar sua solução, pode ignorar o campo "Upload source file".*
