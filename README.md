# Analytics Deliverables: County Education EDA & Duka Electronics H1 2026 Board Report

## 1. Summary of Engagements & How to Run Them

This repository delivers two end-to-end analytics engagements:
1. **Engagement 1 — County Education Office (`student_eda.ipynb`):** Exploratory data analysis of **1,200** learner records (`student_performance.csv`, seed `55`) across six Kenyan counties to identify At-Risk learners (`average_score < 60`), quantify behavioral and structural performance drivers, and guide budget allocation for a targeted learner-support programme.
2. **Engagement 2 — Duka Electronics Board Report (`board_report.ipynb` & `dashboard.md`):** Executive visual storytelling and interactive Looker Studio dashboard covering **1,000** H1 2026 orders (`duka_sales.csv`, seed `2026`, **KES 71,792,500** total revenue), culminating in a mobile-readable single-page board brief (`reports/duka_board_report.png`) and H2 growth recommendations.

### How to Reproduce & Run
1. **Install dependencies:**
   ```bash
   pip install -r requirements.txt

   Regenerate raw datasets (student_performance.csv and duka_sales.csv):

   python generate_data.py

   Execute both notebooks end-to-end:

   jupyter nbconvert --to notebook --execute --inplace student_eda.ipynb
jupyter nbconvert --to notebook --execute --inplace board_report.ipynb

Running student_eda.ipynb exports the three EDA figures into figures/.

Running board_report.ipynb exports figures/before.png, figures/after.png, and reports/duka_board_report.png.

See dashboard.md for the live public Looker Studio dashboard link and filtered screenshots.

Five Key EDA Insights (Engagement 1 · County Education Office) 1. Overall At-Risk Population: Out of 1,200 learners, 8.2% (99 students) fall into the At Risk band (< 60%), while 56.0% (672) are Meeting (60–74%) and 35.8% (429) are Exceeding (≥ 75%). 2. Primary Behavioral Drivers: Weekly study_hours is the strongest predictor of average_score ($r = 0.704$), followed by attendance_rate ($r = 0.359$), and the two habits act independently ($r = -0.029$). 3. Public School Concentration: Public schools account for 94.9% (94 of 99) of all At-Risk learners, with an At-Risk rate of 10.85% compared to just 1.50% in Private schools.4. Persistent Structural School-Type Gap: Private learners outscore Public learners by +5.55 percentage points overall (76.01% vs. 70.46%), and a +3.59 to +7.80 point gap persists across every attendance band and study-hour quartile. 5. County Disparities & Study Slope: Nairobi recorded the highest share of At-Risk learners (9.24%, 17/184) while Turkana posted the lowest county mean score (70.97%); across all students, each extra weekly study hour is associated with +2.12 percentage points ($R^2 = 0.4954$).
Final One-Page Board Report (Engagement 2 · Duka Electronics)
4. Board Summary (145 Words)
In the first half of 2026, Duka Electronics generated KES 71.8 million across 1,000 orders, achieving an average order value of KES 71,792. Performance was anchored by core computing hardware and our flagship capital branch: Laptops (KES 41.5M) and Tablets (KES 19.3M) delivered 84.8% of total revenue, while Nairobi contributed 36.4% (KES 26.1M)—nearly double runner-up Mombasa (KES 14.0M). Monthly sales climbed steadily to an April peak of KES 13.5 million before easing 19.3% to KES 10.9 million in June. While In-store remained our primary channel (57.1%, KES 41.0M), Online sales captured 31.7% (KES 22.8M), including 83 high-value Premium orders in Nairobi and Mombasa worth KES 10.2 million. For H2 2026, leadership should launch targeted online promotions in Nairobi and Mombasa, introduce accessory bundles at Laptop and Tablet checkout to lift attach rates, and run Q3 promotional drives across regional branches to reverse June's softening trend.
