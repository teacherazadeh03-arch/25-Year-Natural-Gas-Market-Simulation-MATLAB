%% ---------------- Energy Demand and Price Forecasting Model ----------------

% Initial values
years = 25;              % Number of years for simulation
income0 = 50000;         % Average household income in $
base_price0 = 3.5;       % Initial natural gas price ($/unit)
demand0 = 700;           % Initial demand (million m3/day or energy unit)
HDD0 = 3000;             % Initial Heating Degree Days (HDD)
pop0 = 50e6;             % Initial population (50 million)
subsidy_rate = 0.5;      % Initial subsidy rate (50%)
subsidy_removal_rate = 0.02;  % 2% annual subsidy removal rate
inflation_rate_nominal = 0.03;  % Nominal inflation rate
demand_growth_baseline = 0.02;  % Baseline demand growth rate
tech_innovation_factor = 0.01;  % Energy efficiency improvement factor
carbon_tax_rate = 0.05;  % Carbon tax applied after year 10

% Population parameters
pop_growth = 0.01;       % Population growth rate (1% per year)

% Price elasticity parameters (income-sensitive, low and high income)
low_income_share = 0.3;  % 30% of population is low-income
high_income_share = 0.7; % 70% of population is high-income
price_elasticity_low = -0.6;
price_elasticity_high = -0.3;

% Heating Degree Days (HDD) parameters
HDD_change = 0.01;  % Annual change in HDD due to climate change

% Behavioral factors
insulation_improve = 0.01;  % 1% increase in insulation efficiency annually
appliance_efficiency_improve = 0.015;  % 1.5% improvement in appliances annually
behavioral_change_factor = 0.005;  % 0.5% demand reduction per year due to behavioral changes

% Arrays to store results
income_arr = zeros(years, 1);
demand_arr = zeros(years, 1);
price_arr = zeros(years, 1);
pop_arr = zeros(years, 1);
HDD_arr = zeros(years, 1);

% ---------------- Yearly Simulation ----------------
for y = 1:years
    % Update population based on growth
    population = pop0 * (1 + pop_growth)^(y - 1);

    % Apply inflation to income
    income = income0 * (1 + inflation_rate_nominal)^(y - 1);

    % Adjust demand based on subsidy reform and energy efficiency improvements
    base_price = base_price0 * (1 - subsidy_rate);  % Adjust price for subsidies
    subsidy_rate = max(subsidy_rate - subsidy_removal_rate, 0);  % Gradually remove subsidy
    
    % Apply energy efficiency improvements for insulation and appliances
    insulation_improvement = 1 + insulation_improve * y;  % Insulation improves each year
    appliance_efficiency = 1 + appliance_efficiency_improve * y;  % Appliance efficiency improves each year
    total_efficiency = insulation_improvement * appliance_efficiency;
    
    % Apply population segmentation (low vs. high income)
    demand_low_income = demand0 * low_income_share;  % 30% of total demand from low-income households
    demand_high_income = demand0 * high_income_share;  % 70% from high-income households

    % Apply price elasticity to each group
    demand_low_income = demand_low_income * (1 + price_elasticity_low * (base_price / base_price0));
    demand_high_income = demand_high_income * (1 + price_elasticity_high * (base_price / base_price0));

    % Total demand for the year
    demand = demand_low_income + demand_high_income;
    
    % Apply behavioral change (smart homes, energy conservation)
    demand = demand * (1 - behavioral_change_factor * y);
    
    % Apply changes in heating degree days (climate effect)
    HDD = HDD0 * (1 + HDD_change * y);

    % Adjust demand based on heating needs and efficiency improvements
    demand = demand * (1 + HDD / HDD0);  % Increase demand if HDD increases (colder weather)

    % Apply technological improvements to demand (energy efficiency)
    demand = demand * total_efficiency;

    % Apply carbon tax after year 10
    if y > 10
        base_price = base_price * (1 + carbon_tax_rate);  % Increase price due to carbon tax
    end
    
    % Store the results for the current year
    income_arr(y) = income;
    demand_arr(y) = demand;
    price_arr(y) = base_price;
    pop_arr(y) = population;
    HDD_arr(y) = HDD;
    
end

% ---------------- Results Visualization ----------------
figure;
subplot(2, 2, 1);
plot(1:years, income_arr, '-o');
title('Income Growth Over Time');
xlabel('Year');
ylabel('Income ($)');

subplot(2, 2, 2);
plot(1:years, demand_arr, '-o');
title('Energy Demand Over Time');
xlabel('Year');
ylabel('Demand (million m3/day)');

subplot(2, 2, 3);
plot(1:years, price_arr, '-o');
title('Energy Price Over Time');
xlabel('Year');
ylabel('Price ($/unit)');

subplot(2, 2, 4);
plot(1:years, pop_arr, '-o');
title('Population Growth Over Time');
xlabel('Year');
ylabel('Population (millions)');

%% ---------------- End of Simulation ----------------
