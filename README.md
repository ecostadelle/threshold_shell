# Fleet Transition Challenge

**Introduction -**

Welcome to the fifth edition of the Shell.ai Hackathon for Sustainable and Affordable Energy. Shell.ai Hackathon brings together brilliant minds passionate about digital solutions and AI, to tackle real energy challenges and help build a lower-carbon world where everyone can access and afford energy.In the previous four editions, we addressed some of the digital challenges around the energy transition: windfarm layout optimization (2020), irradiance forecasting for solar power generation (2021), optimal placement of electric vehicle (EV) charging stations (2022), and supply chain optimization for biorefineries (2023). This year, we focus on fleet decarbonization - a transition problem in the mobility sector.

**Challenge -**

Professional, delivery and operational fleets are a significant contributor to global greenhouse emissions. Fleet owners aspire to achieve net-zero emissions promptly; however, the transition presents a complex dilemma. Balancing the urgency of achieving net-zero emissions with business sustainability and customer satisfaction requires a decision-making framework that considers factors such as timing,location, and approach. In this hackathon, you will have a chance to develop mathematical models to optimize fleet decarbonization strategies, to help fleet owners make informed decisions that align with their energy transition objectives and business outcomes. By harnessing the power of data and mathematical models, you will navigate the complexities of demand forecasts, dissect emission profiles,and find ways to meet ambitious emission targets. The end game is to develop ingenious solutions that strike a balance between operational effectiveness and environmental impact.

**Problem Statement -**

Road transport is the backbone of supply chain, playing a pivotal role in moving goods and bolstering the economy. This mode of transport’s advantages are flexibility, door-to-door service, and connectivity between cities, towns, and villages. While it comes with convenience and advantage, professional, delivery and operational fleets are a significant contributor to global greenhouse emissions. Fleet owners aspire to achieve net-zero emissions promptly; however, the transition presents a complex dilemma. Balancing the urgency of achieving net-zero emissions with business sustainability and customer satisfaction requires a decision-making framework that considers factors such as timing, location, and approach. In this hackathon, you will have a chance to develop mathematical models to optimize fleet decarbonization strategies, to help fleet owners make informed decisions that align with their energy transition objectives and business outcomes. By harnessing the power of data and mathematical models, you will navigate the complexities of demand forecasts, dissect emission profiles, and find ways to meet ambitious emission targets. The end game is todevelop ingenious solutions that strike a balance between operational effectiveness and environmental impact.We will provide various yearly ‘demand’ data from a fleet operator that must be met. The demand data is further divided into various size and distance buckets which indicate what vehicle sizes should be used and how much distance per day they can cover. These are some additional constraints imposed on meeting the customer demand. We provide various vehicles from the following 3 drivetrains: Diesel, LNG, and BEV (Battery Electric Vehicle). For each of these vehicles, the cost, operational yearly range, distance bucket they can cover, and the vehicle ID (unique identifier which helps you reference them in your solution) is provided. We include the information on the fuel consumption by every model of the vehicle and the corresponding fuel types. Furthermore, we also include the cost for every fuel type along with the amount of carbon emissions by each of them, for every single year. Finally, you are also provided with the total carbon emission limits that must not be exceeded every year. All the data provided spans the years 2023 to 2038 (both years inclusive), for a total of 16 years

Your solution should provide an optimal fleet composition over the years, which meets all supply-chain demand and constraints while abiding by the carbon emission limits for every year and has the lowest overall cost possible. The data provided to you and the solution expected from you has been further explained in the next section.

**Data description -**

The dataset contains the following:

- **demand.csv**: This file gives you the total yearly distance demand (in kms) that needs to be satisfied with vehicles of size Sx (size bucket) which can travel at least a minimum of Dx (distance bucket) per day. For example, row 1 indicates that there is a yearly demand of 869181 km for the S1 sized vehicles which can travel at least a minimum of D1 distance bucket per day.
- **vehicles.csv**: This file gives you the vehicle ID (model), type of vehicle (drivetrain), size bucket, year in which you can purchase it, purchase cost, yearly range (in kms), and the daily maximum distance bucket it can travel.
- **vehicles_fuels.csv**: This file gives you the fuel consumption (unit of fuel consumed/km) for every vehicle ID using a certain type of fuel.
- **fuels.csv**: There are 5 fuel types, and for each, this table provides the carbon emission per unit fuel and the (median) cost per unit fuel across all the years. It also includes the uncertainty in the fuel cost.
- **carbon_emissions.csv**: Provides the total carbon emissions limits that should not be violated for every year. It is a decreasing profile over the years.
- **sample_submission.csv**: Provides sample format for submission

The columns provided in the dataset are as follows:

| Column name | Description |
| --- | --- |
| year | 2018, 2019, 20182019 |
| data_type | depot_location, refinery_location, biomass_forecast, biomass_demand_supply, pellet_demand_supply |
| source_index | Within 0 to 2417 |
| destination_index | Within 0 to 2417 |
| value | Any value following problem constraints |

**Notations -**

![Notations](https://he-s3.s3.amazonaws.com/media/uploads/da684fa5-3f31-447e-a544-14cfd8f0dc51.png)

**Objective -**

![Objective](https://he-s3.s3.amazonaws.com/media/uploads/6d5a0bfd-1dab-4f77-b3e2-9400cadd09d4.png)

**Constraints -**

- Vehicle of size Sx can only cater to the demand of size bucket Sx.
- Vehicle belonging to distance bucket Dx can satisfy all demands for distance bucket D1 to Dx. For example, vehicle belonging to distance bucket D4 can satisfy demand of D1, D2, D3, D4 buckets; similarly, D3 can satisfy D1, D2, D3 but NOT D4.
- Total carbon emitted by fleet operations each year should be within the respective year’s carbon emissions limits provided in carbon_emissions.csv. Total carbon emissions for a year is calculated using:

    !Total carbon emissions

- Total yearly demand for each year must be satisfied for each distance and size buckets.
- Vehicle model of year 20xx can only be bought in the year 20xx. For example, Diesel_S1_2026 can only be bought in 2026 and not in any subsequent or previous years.
- Every vehicle has a 10-year life and must be sold by the end of 10th year. For example, a vehicle bought in 2025 must be sold by the end of 2034.
- You cannot buy/sell a vehicle mid-year. All buy operations happen at the beginning of the year and all sell operations happen at the end of the year.
- Every year at most 20% of the vehicles in the existing fleet can be sold.

**Evaluation -**

There will be 2 rounds of evaluation which are as follows:

- Public
- Private

The score generated for the public round will be visible on the leaderboard till the first round is over.

You are expected to provide the solution in a .csv format file. The column names that should exist in the .csv along with “valid” entries are provided in the table below.

| Columns | Valid Entries |
| --- | --- |
| Year | 2023, 2024, ...., 2038 |
| ID | Should be among list of IDs provided in vehicles.csv |
| Num_Vehicles | >=1 |
| Type | Should be among “Buy”, “Use”, “Sell”. |
| Fuel | Should be among “Electricity”, “B20”, “LNG”, “BioLNG”, “HVO”. |
| Distance_bucket | Should be among D1, D2, D3, D4. |
| Distance_per_vehicle(km) | Should >= 0 and <= Yearly range of that model. |

Note: Distance bucket of the solution file corresponds to the distance bucket in the demand.csv file. Note that this is not the distance bucket of the vehicle itself (we get that from vehicles.csv anyways using the provided ID).

**Additional Info -**

- Vehicle resale value, insurance cost and maintenance costs as a percentage of its purchase cost is given below for each year after the purchase of vehicle.

    !Vehicle resale value, insurance cost and maintenance costs

To illustrate the calculations, let us take an example of purchase cost = $100 for a vehicle bought on Jan 1st , 2025. Using the percentages in the above table, the values can be calculated as follows:

    !Values calculation

- Distance bucket mappings -

    !Distance bucket mappings

- Vehicle size bucket mappings -

    !Vehicle size bucket mappings

Please note that insurance and maintenance costs should be calculated for all vehicles in the fleet (irrespective of whether they are used in a particular year), whereas fuel costs are only for those vehicles that will be used (driven) in that year.

**Scoring -**

If your solution satisfies all constraints, we will first calculate your solution’s total cost of fleet ownership and operations using the overall cost function. Your cost (the lower the better) will then be converted to a score (the higher the better) between 30 to 100 using the following transformation function for the leaderboard ranking:

$$
\text{leaderboard score} = \max\left[30, \left(100 - 70 \times \frac{\text{cost}}{\text{reference cost}}\right)\right]
$$

Scores between 0 to 26 are reserved for the error codes detailed below.

As you can see from the fuels.csv, there is a median fuel cost along with an uncertainty band that has been provided. The final cost (which will also comprise of fuel costs), will be a statistical aggregate over 1000 randomly drawn samples from the provided fuel distribution. The public leaderboard is shown to you during the entire duration of the competition. Here, you will be evaluated until the year 2028. The private leaderboard will not be shown to you and will only be revealed at the end of the competition. This is evaluated for the full course of 16 years from 2023 to 2038. The reference cost for private leaderboard is 172,000,000, and for public leaderboard it is 65,000,000.

**Note: Error scores -** if the candidate gets any integer score between 0-26, it means it encountered an error during evaluation.

- **0 -** Any unaccounted error code
- **1 -** Year entry must be of type integer.
- **2 -** ID entry must be a string.
- **3 -** Num_Vehicles entry must be of type integer.
- **4 -** Type entry must be a string.
- **5 -** Fuel entry must be a string.
- **6 -** Distance_bucket entry must be a string.
- **7 -** Distance_driven_per_vehicle(km) must be of type float.
- **8 -** Year entry must be >=2023 and <=2038.
- **9 -** ID must be from the given list of vehicle IDs.
- **10 -** Num_Vehicles must be > 0.
- **11 -** Type must take values among “Buy”, “Sell”, “Use”.
- **12 -** Fuel must be among “Electricity”, “LNG”, “BioLNG”, “HVO”, “B20”.
- **13 -** Distance bucket must be among “D1”, “D2”, “D3”, “D4”.
- **14 -** Distance driven must be >= 0 and <= Yearly range for that model.
- **15 -** Constraint 2 violations.
- **16 -** Constraint 5 violation. Vehicle bought in year YYYY should have YYYY in its ID.
- **17 -** Constraint 6 violation. Vehicle purchased in YYYY can only be used for 10 years.
- **18 -** Demand.csv has the demand pertaining to 16 combinations (S1_D1, S1_D2, ..., S4_D4) for each year. Your solution.csv file should also have all these combinations present.
- **19 -** Constraint 4 violation. For example, in demand.csv for year 2023 S1_D1 demand is 869181 km. In the solutions you provide, sum of all distance travelled in the year 2023 by vehicles with S1 size which satisfy D1 distance demand must be >= 869181 km
- **20 -** You should use the right type of fuel for a given vehicle.
- **21 -** Constraint 8 violation. You must sell only a max of 20% of the fleet every year and nothing more.
- **22 -** You can only "Use" vehicle IDs that you have in fleet.
- **23 -** You can only "Use" as many vehicles that you have in fleet for each ID.
- **24 -** You can only "Sell" vehicle IDs that you have in fleet.
- **25 -** You can only "Sell" as many vehicles that you have in fleet for each ID.
- **26 -** Constraint 3 violation. Total Carbon emission by fleet operations <= Carbon budget for that year.

*You do not need to submit your source code files. When you submit your solution, you can ignore the "Upload source file" field.*

Download dataset
