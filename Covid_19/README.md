# COVID-19 Data Analysis in R

![R](https://img.shields.io/badge/R-276DC3?style=for-the-badge&logo=r&logoColor=white)
![Data Analysis](https://img.shields.io/badge/Data_Analysis-FF6C37?style=for-the-badge)
![COVID-19](https://img.shields.io/badge/COVID--19_Research-8A2BE2?style=for-the-badge)

## Project Overview
Comprehensive analysis of global COVID-19 trends using R programming, focusing on:
- Case distribution across countries
- Testing effectiveness metrics
- Temporal progression patterns
- Data organization techniques

## Dataset Structure
```csv
Date,Country_Region,Tested,Positive,Active,Hospitalized
2020-03-01,US,1000,100,80,15
2020-03-01,UK,800,90,70,12
[...]
```

## 🔍 Key Analyses

### 1. Top Countries Identification
```r
# Get top 10 countries by total cases
covid_top_10 <- covid_df %>%
  group_by(Country_Region) %>%
  summarise(Positive = sum(Positive)) %>%
  arrange(desc(Positive)) %>%
  head(10)
```

### 2. Positivity Rate Calculation
```r
# Calculate and sort by positivity rate
covid_df <- covid_df %>%
  mutate(Positivity_Ratio = Positive/Tested) %>%
  arrange(desc(Positivity_Ratio))
```

## Results

### Top 3 Countries by Positivity Rate
| Rank | Country        | Positivity Ratio | Total Cases | Total Tests |
|------|----------------|------------------|-------------|-------------|
| 1    | United Kingdom | 0.11             | 1,473,672   | 1,669,090   |
| 2    | United States  | 0.10             | 17,282,363  | 18,771,790  |
| 3    | Turkey         | 0.08             | 2,031,192   | 2,539,000   |

### Data Structures
**Country Matrix:**
```r
covid_mat <- matrix(
  c(0.11, 1473672, 166909, 0, 0,
    0.10, 17282363, 1877179, 0, 0),
  nrow = 2,
  dimnames = list(c("UK","US"),
                c("Ratio","Tested","Positive","Active","Hospitalized"))
```

**Analysis List Structure:**
```r
covid_analysis_list <- list(
  metadata = list(
    author = "Your Name",
    date = Sys.Date()
  ),
  results = list(
    top_countries = covid_top_10,
    positivity_rates = positive_tested_top_3
  ),
  visualizations = list(
    plot1 = "top_countries_bar.png",
    plot2 = "daily_trends.png"
  )
)
```

## Visualizations

### Top Countries Bar Chart
![Top Countries](https://via.placeholder.com/600x400?text=Top+10+Countries+COVID+Cases)

**Code:**
```r
ggplot(covid_top_10, aes(x = reorder(Country_Region, Positive), y = Positive)) +
  geom_bar(stat = "identity", fill = "#1f77b4") +
  labs(title = "Top 10 Countries by COVID-19 Cases",
       x = "Country",
       y = "Total Cases") +
  coord_flip() +
  theme_minimal()
```

### Daily Cases Trend
![Daily Trends](https://via.placeholder.com/600x400?text=Daily+Cases+Trend)

**Code:**
```r
ggplot(covid_selected, aes(x = Date, y = daily_positive, color = Country_Region)) +
  geom_line(size = 1.2) +
  scale_x_date(date_labels = "%b %Y", date_breaks = "1 month") +
  labs(title = "Daily COVID-19 Cases by Country",
       x = "Date",
       y = "New Cases",
       color = "Country") +
  theme(legend.position = "bottom")
```

##  Installation & Usage

### Requirements
```r
install.packages(c(
  "dplyr",    # Data manipulation
  "ggplot2",  # Visualization
  "lubridate",# Date handling
  "scales"    # Axis formatting
))
```

### Execution Steps
1. Clone repository:
   ```bash
   git clone https://github.com/yourusername/covid19-analysis.git
   ```
2. Run analysis scripts:
   ```bash
   Rscript analysis/top_countries.R
   Rscript analysis/positivity_analysis.R
   ```
3. Generate reports:
   ```bash
   Rscript -e "rmarkdown::render('Covid19 Analysis.Rmd')"
   ```

## Conclusion
Key findings:
- Significant variation in testing effectiveness between countries
- UK showed highest test positivity rate (11%)
- Clear temporal patterns in case progression
- Flexible data structures enabled multidimensional analysis

## Recommendations
1. **Testing Strategy Review** for high-positivity regions
2. **Resource Allocation** based on trend analysis
3. **Data Standardization** for improved comparisons
4. **Automated Monitoring** of emerging hotspots

## License

---

<div align="center">
  <sub>Created with by [Michel Roland] |</sub>
</div>
