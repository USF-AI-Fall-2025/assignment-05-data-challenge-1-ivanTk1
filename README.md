# x62-data-challenge-student-pathways

1) Data Quality:-----------------------

    Initially, my data quality check suggested that only DISTRICT_CODE had missing values. I used histograms and summary statistics to visualize the distribution of wage values and quickly noticed large spikes at zero, confirming this issue. After accounting for zeros as missing, I identified 2,745 missing DISTRICT_CODE entries and about 17,770 missing wage values in the training set, along with 907 missing DISTRICT_CODE and 5,917 missing wage entries in the test set. This deeper analysis revealed that while most categorical features are complete and reliable, the wage data contains significant gaps that must be cleaned and handled properly to ensure accurate and unbiased modeling results.

2) Range: ---------------------------

    The range analysis showed that categorical columns had limited unique values. DISTRICT_TYPE included three groups (School District, Legislative District, All), DEMO_CATEGORY had five (such as Race and Gender), and STUDENT_POPULATION contained multiple subgroups like Hispanic or Latino and Foster Youth. ACADEMIC_YEAR had only 2018–2019, and AWARD_CATEGORY included four degree types. For numeric columns, DISTRICT_CODE ranged from about 110,000 to 5.8 million, showing slight spikes around 2, 4, and 5 in the graph. From the Graphs we see that the wage columns (WAGE_YEAR1–4) ranged from 0 to roughly 150,000 and were all right-skewed. The vast majority where 0 but most paid salaries were between 20,000 and 40,000, but as the years go by a second spike starts to grow around the 60,000 range.

3) Semantics: ------------------
    Each column provides specific contextual information about district characteristics, demographics, and wage outcomes. DISTRICT_TYPE and DISTRICT_NAME identify the organization and location, while DISTRICT_CODE serves as a numeric identifier. ACADEMIC_YEAR shows the time frame of the data (2018–2019), and DEMO_CATEGORY along with STUDENT_POPULATION describe demographic breakdowns like race, gender, and foster or homelessness status. AWARD_CATEGORY represents educational outcomes, such as degrees or certificates earned.

    From the heatmap, I found that DISTRICT_CODE has no correlation with any wage columns, confirming it functions as an identifier rather than a predictive factor. However, WAGE_YEAR1 through WAGE_YEAR4 are almost perfectly correlated (around 0.99), which I visualized using the correlation heatmap. This means wage outcomes across consecutive years are highly related, suggesting strong year-over-year consistency in earnings data and potential redundancy among those features.

Reflection: ----------------------------------
    1) The most preicitive features where definitly the third wage year. I think this makes intuitive sense since past income strongly predicts future earnings. Among categorical variables, DISTRICT_NAME also showed moderate influence, suggesting that location affect wage outcomes.

    2) Setting aside the third year wage, it shows that the district that you work in has a huge impact on your salary. This just shows that your district will determine the salary which in turn will determine the quality of your techers affecting your education. 

    3) Some features that might shed more light would be things like district/school yearly budget. Maybe things like student tax braket might also tell us how much tax money is funding these schools effecting wage. job field, or where they live might also help. Stuff like that could help the model understand why some people earn more than others instead of just guessing from the limited data we have.