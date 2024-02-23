# DriveThruML

An exploratory data analysis of in-vehicle coupon acceptance. The goal is to determine which driving scenarios and driver attributes predict whether a customer will accept a coupon delivered to their phone while driving. The analysis uses Python with Pandas for data manipulation, NumPy for numerical work, and Seaborn and Matplotlib for visualization, all captured in a single Jupyter notebook.

[Project Notebook](notebook/coupon_analysis.ipynb)

## Data

The dataset is the [in-vehicle coupon recommendation dataset](https://archive.ics.uci.edu/dataset/603/in+vehicle+coupon+recommendation) from the UCI Machine Learning Repository (12,684 survey responses collected via Amazon Mechanical Turk). A copy is included at `dataset/coupons.csv` so the notebook runs without any downloads.

## Key findings

All rates below are acceptance rates within the named group, computed on bar coupons only (2,017 rows).

- 57% of all coupons and 41% of bar coupons were accepted.
- Bar-going frequency is the dominant factor. Drivers who visit a bar more than 3 times a month accepted 77% of bar coupons, versus 37% for those who go 3 or fewer times.
- Drivers who go to a bar more than once a month and are over 25 accepted 70%, versus 33% for all other drivers.
- Frequent bar-goers without a child passenger and outside farming, fishing, and forestry occupations accepted 71%, versus 29% for everyone else.
- Age and marital status add little once bar frequency is known. The data contains no widowed drivers who visit bars more than once a month, so no conclusion about widowed drivers is possible.
- The pattern generalizes: for coffee house coupons, drivers who visit a coffee house more than once a month accepted 66%, versus 35% for those who go once a month or less.

## Limitations

Group frequency answers such as "1~3 visits" are encoded to single representative values (2, 6, 9), so thresholds like "more than once a month" are approximations of the underlying survey buckets. These are observational comparisons, not causal claims, and no significance testing or modeling has been applied yet.

## Running it

```
pip install -r requirements.txt
jupyter notebook notebook/coupon_analysis.ipynb
```

The notebook runs top to bottom with no errors against the included dataset.

## Next steps

Compare age groups and their probability of accepting coupons, compare time of day and passenger type across coupon categories, and add significance tests or a simple classifier to quantify which factors matter most.
