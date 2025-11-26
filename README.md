# The Analysis
## 1. What are the most demanded skills for the top most popular data roles?
To find the most demanded skills , I filtered out those positions by which ones were the most popular, and got the top 5 skills for these top 3 roles.
View my notebook with detailed steps here: [2_Skill_Demand.ipynb](3_Projects\2_Skill_Demand.ipynb)

### Visualize Data
'''python
fig, ax = plt.subplots(len(job_titles), 1)
for i, job_title in enumerate(job_titles):
    df_plot = df_skills_per[df_skills_per['job_title_short'] == job_title].head(5)
    # df_plot.plot(kind='barh', x='job_skills', y='skill_percent', ax=ax[i], legend=False, title = job_title)
    sns.set_theme(style="ticks")
    sns.barplot(data=df_plot, x='skill_percent', y='job_skills', ax=ax[i], hue = 'skill_count', palette='dark:blue_r')
    
    ax[i].set_title(job_title)
    ax[i].set_xlabel('')
    ax[i].set_ylabel('')
    ax[i].legend().set_visible(False)
    ax[i].set_xlim(0, 78)
plt.show()
'''
### Results
![Visualization in form of graphs of Top skills](3_Projects\Images\Skill_Demand_Data.png)

### Insights

## **1. Universal Core Skills (Shared Across All Roles)**

These form the foundation of any data career:

**SQL** – The only true universal skill for Analysts, Scientists, and Engineers.
**Python** – Used for automation, data processing, and modeling (most essential for Scientists).
**Data Visualization** – Tableau/Power BI for Analysts; Python libraries for Scientists; occasional use by Engineers.

---

## **2. Data Analyst – Business & Reporting Focus**

Analysts transform data into insights and dashboards.
**Key Skills:**

* SQL (intermediate), Excel, Tableau/Power BI
* Basic Python/R
* Reporting, storytelling, KPI analysis

**What They Do:** Build dashboards, analyze trends, support business decision-making.

---

## **3. Data Engineer – Systems & Pipelines Focus**

Engineers design and maintain the data infrastructure.
**Key Skills:**

* Python/Scala, SQL
* Cloud platforms (AWS/Azure/GCP)
* Spark, Databricks, Hadoop
* ETL tools (Airflow, dbt, Kafka)
* DevOps basics (Git, Docker, CI/CD)

**What They Do:** Build pipelines, manage data flows, optimize storage systems.

---

## **4. Data Scientist – Modeling & Machine Learning Focus**

Scientists use data to build predictions and statistical models.
**Key Skills:**

* Python (dominant), SQL
* ML libraries (scikit-learn, TensorFlow, PyTorch)
* Statistics, experiment design, feature engineering
* Visualization + communication
* MLOps tools (MLflow)

**What They Do:** Analyze complex patterns, build predictive models, run experiments.

---

## **5. Cloud & Modern Tools (Growing Across All Roles)**

* Analysts → BigQuery, Snowflake, Redshift (data querying)
* Engineers → Deep cloud + infrastructure (IAM, compute, storage)
* Scientists → Cloud ML platforms (SageMaker, Vertex AI)

---

## **6. How the Roles Fit Together**

**Engineers** build data systems → **Scientists** model the data → **Analysts** turn results into decisions.
All three roles depend on each other, forming a complete data ecosystem.

---

