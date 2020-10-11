# School Data Analysis

This project looks at school performance through various lenses. Performance by school, school type, grade-level, and spend-per-student are all considered. 

### Noteable Findings

Charter schools have better overall performance (90.56% passing both math and reading), and spend less per-student than disctrict schools ($598.78 for charter schools vs. $643.09 for district schools). However, charter schools tend to be medium-size (1,000-2000 students), and they typically operate with smaller budgets. 

Spend by School Type: 

| School Type | Avg Spend Per Student |
| ----------- | ----------- |
| Charter | $598.78 |
| District | $643.09 |

Budget by School Size: 

| School Size | Total Budget |
| ----------- | ----------- |
| Small (<1000) | $833,945 |
| Medium (1,000 - 2,000) | $5,147,986 |
| Large (2,000 - 5,000) | $18,667,497 |

Count of Schools by Size:

| School Type | Size | Count | 
| ----------- | ------ | ----- |
| Charter	| Medium (1,000 - 2,000) | 5 |
|       | Small (<1000) |	2 |
|       | Large (2,000 - 5,000)	| 1 |
| District |Large (2,000 - 5,000)	| 7 |

## About Additional Code 

Some of the tables above show analyses that were not required but, I believe, provide insight. 

To start, to look for school size and budget, I simply created a dataframe only because it looks nicer than a series: 

    school_size_budget_df = pd.DataFrame(school_summary_df.groupby(["School Size"])["Total Budget"].sum())

Next, I wanted to look for the count of schools that fall into the school-size bins: 

    school_size_counts_df = pd.DataFrame(school_summary_df.groupby(["School Type"])["School Size"].value_counts())

This shows that small and medium sized schools tend to be charter schools for this dataset, and they tend to have smaller budgets. This is insightful when considering the average spend per-student for each school type (as seen in the final table): 

    school_type_budget = round((school_data.groupby("Type")["Budget"].sum() / number_type_students), 2)

Of course it would make sense for charter schools to spend less money per-student since they tend to have smaller budgets and be small-to-medium in size. More analysis needs to be done, but when looking at the total budget by school type, it seems that charter schools are $10 million cheaper and provide better outcomes. 

    school_type_budget_df = pd.DataFrame(school_summary_df.groupby(["School Type"])["Total Budget"].sum())

Count of Schools by Size:

| School Type | Total Budget | 
| ----------- | ------ | 
| Charter	| $7,301,505 |
| Disctrict | $17,347,923 |