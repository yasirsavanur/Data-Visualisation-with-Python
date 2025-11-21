# Visualising US Domestic Flight Performance (1987–2020)

This project explores how domestic US flights perform over time, with a focus on delays and cancellations.

I use a sample of the **US domestic on-time performance dataset** (1987–2020) and build a set of Plotly and Dash dashboards to answer simple questions like:

- How many flights are airlines operating each year?
- How does performance change across states?
- What actually causes delays (carrier, weather, NAS, security, late aircraft)?
- How did things change in more recent years (2015–2020), especially around 2020?

The project is meant to be a hands-on data visualisation and dashboarding exercise, not a super formal academic study.

---

## Objectives

The main goals of this project are:

- To practice **exploratory data analysis (EDA)** on a real aviation dataset.
- To build **interactive visualisations** using Plotly and Dash.
- To break down **flight delays by cause** and see how they change over time.
- To summarise a few **high-level insights** about recent years (2015–2020).

---

## Dataset

The data comes from the **Reporting Carrier On-Time Performance** dataset (US domestic flights, 1987–2020).

Each row represents a single flight and includes (among many others):

- Flight date, year, month, day of week  
- Reporting airline (carrier)  
- Origin and destination states  
- Scheduled and actual departure / arrival times  
- Delay information split by cause:
  - `CarrierDelay`
  - `WeatherDelay`
  - `NASDelay` (National Airspace System)
  - `SecurityDelay`
  - `LateAircraftDelay`
- Cancellation and diversion flags

In this repo I work with a **sample of 27,000 flights** saved as:

- [`airline_data.csv`](airline_data.csv)

This is enough for exploration and visualisation without killing your laptop.

---

## Project Structure

Key files and folders (clickable):

- [`airline_data.csv`](airline_data.csv)  
  Sample of the airline on-time performance dataset.

- [`US Flights - Plotly.ipynb`](US%20Flights%20-%20Plotly.ipynb)  
  Jupyter notebook where I experiment with Plotly charts (bar, pie, histogram, line, sunburst, etc.).

- [`US Flights - dash_basics.py`](US%20Flights%20-%20dash_basics.py)  
  Basic Dash app to display static charts laid out in a simple dashboard.

- [`US Flights - dash_interactivity.py`](US%20Flights%20-%20dash_interactivity.py)  
  Dash app with user input (year selection) to update charts interactively.

- [`9) flight_delay.py`](9%29%20flight_delay.py)  
  Dash app focused on **delay components** (carrier, weather, NAS, security, late aircraft) by month and airline.

- [`Yearly Flight Performance-Delay Report/Yearly Performance:Delay Report.py`](Yearly%20Flight%20Performance-Delay%20Report/Yearly%20Performance%3ADelay%20Report.py)  
  Main Dash application combining:
  - A **Yearly Flight Performance** view.
  - A **Yearly Flight Delay** view.

- `Yearly Flight Performance-Delay Report/Flight Performance Report Dashboard Screenshots/`  
  Saved screenshots of the yearly performance dashboards (bar, line, pie, choropleth, block charts).

- `Yearly Flight Performance-Delay Report/Flight Delay Report Dashboard Screenshots/`  
  Saved screenshots of the yearly delay dashboards (line charts by delay type, 2015–2020).

- `8 - plot(x).png`, `9 - plot(x).png`, `dash - plot.png`  
  Extra static plots from intermediate exercises and experiments.

---

## How to Run the Dash Apps

You’ll need Python and a few core libraries:

- `pandas`
- `plotly`
- `dash`

Install dependencies (example):

```bash
pip install pandas plotly dash
```

Then run, for example, the main yearly report dashboard:

```bash
python "Yearly Flight Performance-Delay Report/Yearly Performance:Delay Report.py"
```

or the delay-focused app:

```bash
python "9) flight_delay.py"
```

Dash will print a local URL (usually `http://127.0.0.1:8050/`) – open that in your browser to interact with the dashboard.

---

## Visualisations

Below are some of the key visualisations, with links to the screenshots stored in this repo.  
You can replace or rearrange these in the README as you like.

### 1. Yearly Flight Performance (2015–2020)

#### 1.1 Flights by reporting airline (example: 2019)

Bar chart showing how flights are distributed across airlines in a given year.

![Bar chart – flights by reporting airline (2019)](Yearly%20Flight%20Performance-Delay%20Report/Flight%20Performance%20Report%20Dashboard%20Screenshots/Bar%20Chart%20-%202019.png)

This gives a quick snapshot of which carriers dominate traffic in the sample.

#### 1.2 Monthly flight counts over time

Line charts help show how busy each year is and how flights fluctuate across months.

![Line graph – monthly flight counts (2019)](Yearly%20Flight%20Performance-Delay%20Report/Flight%20Performance%20Report%20Dashboard%20Screenshots/Line%20Graph%20-%202019.png)

You can see seasonal patterns (busier periods vs quieter months) and compare that with other years like 2015 or 2020.

#### 1.3 Geographic distribution of flights

Choropleth maps show how flights are spread across US states.

![Choropleth – flights by destination state (2019)](Yearly%20Flight%20Performance-Delay%20Report/Flight%20Performance%20Report%20Dashboard%20Screenshots/Choropleth%20Map%20-%202019.png)

This makes it easy to spot which regions receive more traffic and which are relatively quiet.

#### 1.4 Flight mix and share by airline

Pie and block charts show the share of flights by airline or other categories.

![Pie chart – share of flights by airline (2019)](Yearly%20Flight%20Performance-Delay%20Report/Flight%20Performance%20Report%20Dashboard%20Screenshots/Pie%20Chart%20-%202019.png)

![Block chart – flight distribution (2019)](Yearly%20Flight%20Performance-Delay%20Report/Flight%20Performance%20Report%20Dashboard%20Screenshots/Block%20Chart%20-%202019.png)

These give a more “at a glance” view of how the sample is split across carriers.

---

### 2. Yearly Delay Dashboards (2015–2020)

The second part of the project focuses on **delay types**.  
The Dash app computes average monthly delays by airline and delay category for a selected year.

For each year from 2015 to 2020 you’ll find line charts like:

![Carrier delay – 2019](Yearly%20Flight%20Performance-Delay%20Report/Flight%20Delay%20Report%20Dashboard%20Screenshots/%28Line%29%20Carrier%20delay%20-%202019.png)

![Weather delay – 2019](Yearly%20Flight%20Performance-Delay%20Report/Flight%20Delay%20Report%20Dashboard%20Screenshots/%28Line%29%20Weather%20delay%20-%202019.png)

![NAS delay – 2019](Yearly%20Flight%20Performance-Delay%20Report/Flight%20Delay%20Report%20Dashboard%20Screenshots/%28Line%29%20NAS%20delay%20-%202019.png)

![Security delay – 2019](Yearly%20Flight%20Performance-Delay%20Report/Flight%20Delay%20Report%20Dashboard%20Screenshots/%28Line%29%20Security%20delay%20-%202019.png)

![Late aircraft delay – 2019](Yearly%20Flight%20Performance-Delay%20Report/Flight%20Delay%20Report%20Dashboard%20Screenshots/%28Line%29%20Late%20Aircraft%20delay%20-%202019.png)

You can swap the year in the filename (2015–2020) to show other years.

---

### 3. Plotly Notebook Experiments

The notebook [`US Flights - Plotly.ipynb`](US%20Flights%20-%20Plotly.ipynb) contains smaller one-off charts used to get familiar with Plotly:

- Flights by destination state
- Percentage of flights by reporting airline
- Histograms of arrival delay
- Monthly cancellation trends
- Sunburst plots combining month and destination state

Example image slots (these point to the PNGs saved during those exercises):

![Dash layout experiment](dash%20-%20plot.png)

![Exercise 8 – plot 1](8%20-%20plot%281%29.png)  
![Exercise 8 – plot 2](8%20-%20plot%282%29.png)

![Exercise 9 – delay dashboard snapshot](9%20-%20plot%281%29.png)

These are mainly for practice and for showing intermediate steps in the learning process.

---

## Key Findings (High Level)

This is not a full research paper, but a few simple patterns show up clearly in the visualisations and in the data sample used:

- **Flight volume changes over time**  
  - Recent years (2015–2019) show steady traffic in the sample.
  - 2020 has a **sharp drop in flight counts** and noticeably different behaviour, which lines up with the impact of COVID-19.

- **Most delays come from carrier and late aircraft issues**  
  - In the 2015–2020 window, `CarrierDelay` and `LateAircraftDelay` are consistently the largest delay components on average.
  - `NASDelay` also contributes a fair amount, while **security delays are almost negligible** in comparison.
  - Weather delays are visible but not the main driver most of the time.

- **Seasonal behaviour in delays**  
  - Average arrival delays fluctuate by month.  
  - Some months show spikes (for example, late winter or summer), while others even show **negative average arrival delays** (flights arriving slightly early on average).
  - This variation matches what you might expect from holidays, weather seasons, and traffic patterns.

- **Geographic concentration of traffic**  
  - The choropleth maps show that a handful of states handle more traffic in the sample, reflecting major hubs and popular routes.
  - Less populated states naturally see fewer flights.

Overall, the dashboards give a quick way to answer:

> “How busy are flights this year, where are they going, and what is actually causing the delays?”

instead of digging through raw CSV files.

---

## Possible Extensions

Some ideas to extend this project:

- Add **filters** in the Dash app for:
  - specific airlines,
  - origin / destination states,
  - or time windows (e.g. peak months only).
- Include metrics like:
  - on-time arrival rate (% of flights with small or zero delay),
  - cancellation rate by airline or state.
- Compare **pre-2020 vs 2020** more explicitly to highlight the impact of the pandemic.
- Deploy the Dash app to a platform like Render, Railway, or Heroku and link it from this README.

---

## Author

**Yasir Savanur**

- LinkedIn: https://www.linkedin.com/in/yasir-savanur/

This repo is based on exercises around the IBM Developer Skills Network airline dataset and extended with additional visualisations and Dash dashboards.
