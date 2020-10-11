# School Data Analysis

This project looks at school performance through various lenses. Performance by school, school type, grade-level, and spend-per-student are all considered. 

### Noteable Findings

Charter schools have better overall performance (90.56% passing both math and reading), and spend less per-student than disctrict schools ($598.78 for charter schools vs. $643.09 for district schools). However, charter schools tend to be medium-size (1,000-2000 students), and they typically operate with smaller budgets. 

    school_size_budget_df = pd.DataFrame(school_summary_df.groupby(["School Type"])["Total Budget"].sum()
    school_size_budget_df

## About the coding of the project
  school_size_budget_df = pd.DataFrame(school_summary_df.groupby(["School Type"])["Total Budget"].sum()
  school_size_budget_df