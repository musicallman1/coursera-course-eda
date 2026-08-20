# Coursera Course Dataset: Exploratory Data Analysis

Exploratory data analysis of Coursera's course catalog, examining what drives course popularity and how organization type, difficulty, and ratings relate to enrollment.

## Dataset

[Coursera Course Dataset](https://www.kaggle.com/siddharthm1698/coursera-course-dataset) via Kaggle (891 courses, 7 features: title, organization, certificate type, rating, difficulty, and enrollment). Licensed under [GPL-2.0](https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html) — see `LICENSE`.

## What's in the notebook

1. **Data cleaning** — dropped a leftover index column, renamed inconsistent column names, standardized certificate-type casing, and converted enrollment figures from shorthand strings (e.g. `"5.3k"`, `"1.2m"`) to numeric values.
2. **Course organizations** — which organizations publish the most courses, and what mix of course types (Course / Specialization / Professional Certificate) they offer.
3. **Course ratings** — the overall rating distribution, and how it varies by difficulty level.
4. **Course titles & rating** — enrollment patterns across the highest- and lowest-rated courses.
5. **Enrollment by organization type** — comparing academic institutions (universities, colleges) against corporate organizations (e.g. IBM, Google) on rating and enrollment.
6. **Title keyword analysis** — the most common two-word phrases in course titles, and which of those phrases correlate with higher enrollment.

## Key findings

- Course ratings cluster tightly between 4.6 and 4.8, with beginner-level courses making up the majority of offerings and rating well.
- Popularity and rating are related but not tightly coupled — some lower-rated courses still draw strong enrollment, suggesting other factors (organization reputation, topic demand) are at play.
- Academic organizations account for a large share of high-enrollment courses.
- "Data science," "machine learning," and "google cloud" are the most common two-word phrases in course titles, and courses built around these phrases drive disproportionately high enrollment.

## Tools

`pandas`, `numpy`, `seaborn`, `matplotlib`, `plotly`

## How to run

```bash
pip install -r requirements.txt
jupyter notebook coursera_eda.ipynb
```

**Note:** several charts use Plotly for interactivity, which won't render on GitHub's static notebook preview. Open the notebook locally, or via [nbviewer](https://nbviewer.org), to interact with them.

## Repository structure

```
coursera-course-eda/
├── README.md
├── LICENSE
├── requirements.txt
├── data/
│   └── coursea_data.csv
└── notebooks/
    └── coursera_eda.ipynb
```

## Future work

- Feature-engineer boolean topic flags (e.g. `is_tech`, `is_business`) from course titles to test whether specific subject areas drive platform growth.
- Calculate a Bayesian/weighted rating (IMDb-style) that accounts for enrollment volume, to produce a more reliable "best courses" ranking than raw average rating.
- Explore the relationship between Courses and Specializations more directly — how enrollment and completion compare across the two formats.
