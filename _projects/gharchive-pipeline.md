---
layout: page
title: GitHub Archive Data Pipeline
description: End-to-end batch pipeline and dashboard for GitHub activity data
importance: 5
category: engineering
github: https://github.com/GbotemiB/gharchive_de_project
---

An end-to-end data engineering project on [GitHub Archive](https://www.gharchive.org/) data. It answers questions such as which repositories get the most contributions, and at what times users push commits most.

- **Infrastructure**: provisioned on Google Cloud with Terraform.
- **Orchestration**: Prefect flows fetch the data in batches into a Google Cloud Storage data lake.
- **Processing**: PySpark preprocesses the data and loads it into BigQuery, and dbt transforms it for analysis.
- **Dashboard**: developer activity trends in [Looker Studio](https://lookerstudio.google.com/reporting/e3e5216b-45c4-48c7-8bdd-d65ab5431177).

Built with Terraform, Prefect, PySpark, dbt, BigQuery and Looker Studio.
