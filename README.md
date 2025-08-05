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
Reddit News ETL Pipeline using Reddit API and Google BigQuery
This project automates the extraction, transformation, and loading (ETL) of trending news posts from multiple Reddit subreddits into Google BigQuery for centralized storage and analysis.

🔧 Tech Stack & Tools Used
Python for scripting and orchestration

Reddit API with OAuth2 authentication for data access

Pandas for data transformation

Google BigQuery for cloud-based data warehousing

Google Cloud Storage & google-auth for authentication and credentials management

Logging module for traceability and job tracking

Config file (news_config.py) to abstract secrets, endpoints, and schemas

🧩 Pipeline Breakdown
Authentication:

OAuth2 token is generated via Reddit API using client credentials stored in news_config.py.

Data Extraction:

Pulls the top 100 posts from several subreddits (e.g., r/news, r/nottheonion, r/upliftingnews, etc.).

Fetches post metadata such as title, score, upvote_ratio, num_comments, and domain.

Transformation:

Standardizes all subreddit responses into clean Pandas DataFrames.

Adds a dt_updated timestamp column for tracking update time.

Loading to BigQuery:

Before new loads, deletes records from the current date to ensure clean appends.

Loads all subreddit-specific DataFrames into their respective BigQuery tables using an explicit schema.

🚀 Key Features
Designed to be modular and scalable, supporting easy addition of new subreddits.

Uses WRITE_APPEND for continuous historical data storage while maintaining freshness by clearing daily records before reload.

Implements robust logging for transparency in data ingestion and debugging.

Maintains clean data separation across multiple tables, one for each subreddit.
