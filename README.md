# Mint Project Description
I strongly believe in using data as a tool to enhance daily decision-making. In my personal life, one of the most impactful applications of this mindset has been building an end-to-end financial tracking and analysis pipeline to better understand my household’s spending, saving, and investment behavior.

Several years ago, I discovered Mint, a financial aggregator that connects to various accounts to provide a unified view of personal finances. To go beyond the native interface, I utilized mintapi, an unofficial Python SDK built on Selenium, to programmatically access transaction and investment data in real time across all linked accounts. Given the nature of the tool, I ensured compatibility by configuring and maintaining a Selenium-compatible browser setup (specifically, ChromeDriver).

To operationalize this data, I designed and implemented a pipeline that:

Extracts structured and nested financial records in JSON format from Mint

Uploads the data to Google Cloud Storage (GCS)

Loads and structures it into a BigQuery dataset using a predefined schema with nested fields

Enables SQL-based querying and trend analysis over time

This system allows me to build customized dashboards, uncover overspending patterns, forecast recurring expenses, and optimize budgeting strategies. By automating this workflow, I’ve effectively created a self-sustaining analytics environment that empowers me to make data-driven financial decisions and stay on top of my financial goals with minimal manual effort.

This project reflects my belief that even small-scale data engineering solutions can yield meaningful improvements when aligned with everyday needs.


# Reddit News Project Description
Throughout my undergrad I was obssessed with going through sub reddits, I'm still a news junkie. One of my favorite places to get news is Reddit, due to the intuitive aggregation and interactive comments sections.

While the original build for the Reddit connection was straightforward, it was one of the first ETL pipelines I built as a side project last year after deep diving into this topic more . I recently revisited the pipeline and refactored it according to best coding practices.
