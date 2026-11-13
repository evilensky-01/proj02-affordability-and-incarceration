# Project 02 Proposal: <your project title>

**Team members:** <name(s)>

See the [Project 02 instructions](https://data385.github.io/project/proj02_wholegame.html) for what goes in each section. Bullet points are great. Put any images in an `img/` folder.

## 1. Problem statement

_Who has the problem, what decision or need it involves, why it matters, and what you expect to find._

Social welfare programs in theory help mitigate crime and poverty. Assessing affordable housing's affect on 
incarcerated population levels could potentially indicate an economic insurance against the costs surrounding 
jailing, court fees, regular imprisonment costs, and damages from crime. I expect to find that areas with more
affordable housing will have lower incarceration rates.

## 2. Research question

_A clear association between a response and at least one predictor variable._

How do number of available section 8 housing units and percent occupied affect the incarceration rate by county?

## 3. Data acquisition

_In 1-2 sentences, describe the data you intend to collect and how you will get it._

There are two data sets I will be using: the Vera Institute's "Incarceration and Inequality Public Data"
GitHub repository, and the United States Department of Housing and Urban Development, Office of Policy
Development and Research "Picture of Subsidized Households" data, both of which are publicly available for
download.

### a. Confirm viability

_Scraping: summarize the "Before You Scrape" checklist. Downloading: citation, link to the documentation, and how the data were originally collected. Collecting it yourself: how you are collecting it and where you are storing it._

- Citation: Vera Institute of Justice (2025). Incarceration and Inequality Public Data [Data set]. https://github.com/vera-institute/incarceration-inequality-public.
  - How was it collected: Vera sourced the incarceration data from Vera’s existing Incarceration 
  Trends project.Vera sourced demographic data from the U.S. Census American Community Survey (ACS).
  The research team sourced economic data from the U.S. Census Small Area Income and
  Poverty Estimates (SAIPE), Census of Business Patterns (CBP), and ACS datasets, and the
  U.S. Bureau of Labor Statistics Local Area Unemployment Statistics (LAUS) and Alternative
  Measures of Labor Underutilization for States (STALT) datasets.
- Citation: Office of Policy Development and Research. (2026). Picture of subsidized households: 2025 [Data set]. U.S. Department of Housing and Urban Development. https://www.huduser.gov/portal/datasets/assthsg.html.
  - How was it collected: Data on households were sent by agencies and landlords to HUD, and were 
  summarized by HUD. Data on the number of units available and units occupied are from HUD's own 
  administrative records.

### b. Variables of interest

_If you do not have the data yet, list the variables you plan to collect and the exact question text. Include 1) the variable name, 2) data type 3) description. Use bullet points._

- vera_total_jail_pop (Vera); numeric; total jail population in a county in a given year
- total_units (HUD); numeric; number of units under contract for federal subsidy and available for occupancy
- total_occupied (HUD); numeric; number of occupied units under contract for federal subsidy
- vera_white_jail_pop (Vera): numeric; white jail population in a county in a given year
- county_name (Vera): character; county name
- region (Vera): character; region of the United States, characterized by South, West, Midwest, and Northeast

## 4. Data example

_Scraping: a URL and an annotated screenshot. Downloading: a link to your rendered `data_management.pdf` with `glimpse()`. Collecting: a screenshot of one example row._

[Here is my qmd](data_management.qmd) and the [rendered pdf](data_management.pdf).

## 5. EDA

_The techniques and functions you plan to use to import, wrangle, visualize, and explore the data, and why each is needed._

- Import: read_xlsx() and read_csv()
- Wrangle: filter() and inner_join(); the goals are to filter the HUD data to only section 8 program information,
  filter the Vera data to be only 2025 data, and then use inner_join() on the variables in each data set that
  refer to the county name. Since the HUD data was downloaded as california only, there shouldn't be a need to
  filter the counties.
- Visualizing and Exploring: I will use ggplot for most of my data exploration in my primary variables of choice,
  using geom_point() for the numeric relationships, but likely a stacked bar chart to visualize racial demographics
  in incarceration rates. It will be important to consider missing data, because both of these data sets have it. However,
  Vera's is coded as NA, while HUD's is coded as -1.

## 6. Modeling

_The models you plan to use, your response and predictor variables, and why the models fit your research question._



## 7. Communicate

_How you plan to present your results (website, poster, or short slide presentation)._


## 8. LLM disclaimer

_Whether and how you will use AI tools: the specific tool, its use, and your data protection methods. If you won't use any, say so._

