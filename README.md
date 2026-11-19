<div align="center">

# HR Work Environment & Employee Morale Analysis

**A statistical modeling project exploring how workplace support factors relate to employee morale.**

[![Language](https://img.shields.io/badge/language-R-blue)](https://www.r-project.org/)
[![Report](https://img.shields.io/badge/report-R%20Markdown-1f6feb)](group_assignment_hr_morale.html)
[![Analysis](https://img.shields.io/badge/project-statistical%20analysis-6f42c1)](#methodology)
[![License](https://img.shields.io/badge/license-not%20specified-lightgrey)](#license)

</div>

## Overview

This project investigates the analytical statement **“Positive work environment improves employee morale”** using a simulated HR employee attrition dataset. It examines whether factors such as environment satisfaction, relationship satisfaction, work-life balance, overtime, and business travel are associated with employee morale.

The analysis is implemented in R Markdown and includes data preparation, exploratory analysis, statistical tests, and predictive models. The included HTML file is a rendered report of the analysis.

> **Important:** The dataset is described in the report as simulated experimental data derived from a copy of an HR dataset. Findings are for demonstrating statistical methods and should not be interpreted as evidence about real employees or as proof of causation.

## Key Features

- **Data preparation:** checks for missing values, removes identifier and constant columns from the analysis, encodes categorical variables, and creates derived measures.
- **Composite indices:** constructs a work-environment `Support_Index` and an employee `Morale_Index` from standardized variables.
- **Exploratory analysis:** summarizes numeric and categorical variables and visualizes distributions, group differences, correlations, and the relationship between support and morale.
- **Distribution fitting:** demonstrates Normal, Gamma, Poisson, and Bernoulli distribution fitting for selected variables.
- **Inferential statistics:** applies ANOVA, t-tests, a two-proportion test, variance tests, and Pearson correlation.
- **Predictive modeling:** fits a multiple linear regression model with backward AIC selection and a Naive Bayes morale-category classifier.
- **Example prediction:** includes an editable employee profile used to demonstrate model-based morale predictions.
- **Rendered report:** provides an HTML version of the analysis for convenient browsing.

## Dataset

The project includes `HR-Employee-Attrition.csv`. The rendered report describes it as a simulated HR employee attrition dataset and reports **1,470 rows**.

The analysis considers workplace support variables such as:

- Environment satisfaction
- Relationship satisfaction
- Work-life balance
- Overtime
- Business travel

Morale is represented by a composite index built from job satisfaction, job involvement, performance rating, and retention tendency (the inverse of attrition).

## Tech Stack & Methodology

- **Language:** R
- **Report format:** R Markdown, rendered to HTML
- **Analysis packages:** `tidyverse`, `MASS`, `car`, `e1071`, `corrplot`, `nortest`, `caret`, and `fitdistrplus`
- **Report tooling:** `rmarkdown` and `knitr`

The report follows a data-analysis workflow:

1. Load and prepare the CSV data.
2. Derive support and morale measures.
3. Perform descriptive summaries and visual exploration.
4. Run inferential tests using a significance level of 0.05.
5. Fit and evaluate regression and Naive Bayes models.
6. Summarize findings and limitations.

## Project Structure

```text
HR_Dataset_Analysis-main/
├── HR-Employee-Attrition.csv          # Dataset used by the report
├── group_assignment_hr_morale.Rmd     # R Markdown analysis source
├── group_assignment_hr_morale.html    # Rendered HTML report
├── TPSM-Final.Rproj                   # RStudio project file
└── README.md                          # Project overview and setup
```

## Prerequisites

- [R](https://www.r-project.org/)
- [RStudio Desktop](https://posit.co/download/rstudio-desktop/) (recommended)
- The R packages listed in the [Tech Stack](#tech-stack--methodology) section

The R Markdown source also defines PDF output. Rendering to PDF may require a LaTeX installation; HTML output is available without setting up PDF rendering.

## Setup & Run

1. Clone the repository:

   ```bash
   git clone <repository-url>
   ```

2. Open the cloned project folder and open `TPSM-Final.Rproj` in RStudio.

3. Install the report and analysis packages if they are not already installed:

   ```r
   install.packages(c(
     "rmarkdown", "knitr", "tidyverse", "MASS", "car",
     "e1071", "corrplot", "nortest", "caret", "fitdistrplus"
   ))
   ```

4. Render the HTML report from the project directory:

   ```r
   rmarkdown::render("group_assignment_hr_morale.Rmd", output_format = "html_document")
   ```

   Alternatively, open `group_assignment_hr_morale.Rmd` in RStudio and select **Knit**.

5. Open `group_assignment_hr_morale.html` in a browser to read the report.

The R Markdown source expects `HR-Employee-Attrition.csv` to be in the project directory. It also contains code that attempts to install missing analysis packages when the report is run.

## Using the Analysis

- Read the existing report by opening `group_assignment_hr_morale.html`.
- To rerun or modify the analysis, edit `group_assignment_hr_morale.Rmd` and render it again.
- To try the example prediction, edit the `new_employee` values in the **New Employee Prediction** section of the R Markdown source, then rerun the report.
- The example prediction uses models fitted from the included dataset; it is for demonstration and is not an HR decision-making tool.

## Limitations

- The dataset is described as simulated, so results should not be generalized to real-world employees.
- Composite indices give equal weight to their component variables.
- Statistical significance does not necessarily mean an effect is practically important.
- Naive Bayes assumes conditional independence between features.
- Satisfaction and morale measures are proxies for complex human experiences.

## Roadmap

- Document reproducible package and R version requirements.
- Add a project-specific license.
- Expand the report with additional model validation and interpretation.
- Improve the explanation of how the simulated data was created.

## License

No license is currently specified in the project files. Until a license is added, reuse and redistribution permissions are not defined. Add a `LICENSE` file and update this section if you choose to license the project.

## Author

**Group TPSM Project Division**

This project was created as an IT3011 Theory and Practices in Statistical Modeling group assignment.
