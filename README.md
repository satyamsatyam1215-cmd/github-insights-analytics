GitHub Insights Analytics

A Python and Power BI project that collects GitHub profile, repository,
traffic, and programming-language data through the GitHub REST API and
converts it into structured datasets for analysis.

Project Overview

GitHub provides useful information about repositories, profile activity,
and repository traffic, but the information is spread across different
areas.

I built this project to bring that information together into a single
data workflow.

The project collects GitHub data using Python, prepares it with Pandas,
stores it in SQLite, exports it into CSV files, and uses the resulting
data to build a Power BI analytics report.

Workflow

GitHub API → Python → Pandas → Data Cleaning → SQLite / CSV → Power
BI

GitHub Personal Access Token

This project requires a GitHub Personal Access Token (Fine-grained
PAT) to access GitHub API data.

How to create a GitHub Token

Sign in to GitHub.

Go to Settings.

Open Developer settings.

Select Personal access tokens → Fine-grained tokens.

Click Generate new token.

Enter a token name and expiration date.

Select your GitHub account as the resource owner.

Select the repositories you want to analyse.

Give the token the required read-only repository permissions.

Generate the token.

Copy the token and keep it private.

For repository traffic data, the GitHub API requires the appropriate
repository access. Use the minimum permissions required for your account
and repositories.

GitHub Documentation

Creating a fine-grained personal access
token

GitHub REST API
Authentication

Repository traffic
API

Add the Token

Open Pyhton Code.ipynb and update the first cell:

GITHUB_USERNAME = "your-github-username"
GITHUB_TOKEN = "your-github-token"

Example:

GITHUB_USERNAME = "satyamsatyam1215-cmd"
GITHUB_TOKEN = "YOUR_TOKEN_HERE"

Security: Never upload your real GitHub token to GitHub. If a
token is accidentally exposed, revoke it immediately and generate a
new one.

How to Use

1. Clone or download the repository

Download the project to your local machine.

2. Install the required Python libraries

pip install requests pandas

3. Open the notebook

Open:

Pyhton Code.ipynb

4. Add your GitHub username and token

Update the first cell with your own GitHub username and Personal Access
Token.

5. Run the notebook

Run the notebook cells from top to bottom.

The notebook will collect the GitHub data and generate the following
datasets:

df_user.csv
df_repositories.csv
df_traffic.csv
df_languages.csv

It also creates:

github_analytics.db

Data Files

df_user.csv

Contains GitHub profile-level information.

The dataset is used for analysing information such as:

GitHub username

Profile information

Followers

Following

Public repositories

Account-related statistics

df_repositories.csv

Contains repository-level information collected from the GitHub API.

It includes information such as:

Repository name

Repository ID

Description

Visibility

Creation date

Last update

Default branch

Primary language

Stars

Watchers

Repository size

Repository metadata

df_traffic.csv

Contains repository traffic data collected from GitHub.

Main fields include:

Repository ID

Repository name

Date

Views

Unique visitors

Clones

Unique cloners

This dataset is used to analyse repository traffic and visitor activity.

df_languages.csv

Contains programming-language information for repositories.

Main fields include:

Repository ID

Repository name

Language

Bytes

This dataset helps analyse the programming languages used across the
repositories.

SQLite Database

The notebook also stores the collected data in:

github_analytics.db

The database contains four tables:

user
repositories
traffic
languages

This provides a structured database version of the collected GitHub
data.

What the Python Code Does

The notebook performs the complete data collection and preparation
process.

1. Connects to GitHub

Python's requests library is used to connect to the GitHub REST API
using the username and token.

2. Collects Profile Data

The GitHub user API is used to collect profile-level information.

3. Collects Repository Data

The project retrieves the repositories owned by the GitHub account.

4. Collects Repository Traffic

For each repository, the code retrieves:

Views

Unique visitors

Clones

Unique cloners

Traffic date

5. Collects Programming Languages

For each repository, the GitHub languages endpoint is used to collect
language and byte information.

6. Creates Pandas DataFrames

The collected information is converted into:

df_user
df_repositories
df_traffic
df_languages

7. Cleans the Data

Unnecessary API fields and URL-related fields are removed from the
profile and repository datasets to make the data easier to analyse.

8. Stores the Data

The cleaned DataFrames are stored in SQLite and exported as CSV files.

Power BI Report

The collected datasets are used to create a Power BI dashboard for
GitHub analytics.

The report provides an overview of:

GitHub Profile

GitHub ID

Followers

Following

Public repositories

Account age

Repositories per year

Traffic Overview

Total views

Total clones

Unique visitors

Unique cloners

Average daily views

Peak daily views

Active traffic days

Repositories with traffic

GitHub Traffic Trend

The dashboard shows views and clones over time to understand changes in
repository traffic.

Repository Performance

Repositories can be compared using:

Views

Visitors

Clones

Interactions

Activity

Top Repositories

The report identifies repositories receiving the highest number of views
and provides a comparison of repository performance.

Why I Built This Project

I built this project because I wanted to understand my GitHub account
through data.

Instead of manually checking different GitHub pages for repository
information and traffic, I wanted to collect the information into
structured datasets and analyse it in one place.

The project helps answer questions such as:

Which repositories receive the most views?

How many visitors are coming to my repositories?

Which repositories are being cloned?

How does repository traffic change over time?

Which repositories have more activity?

Which programming languages are used across my repositories?

What does my overall GitHub profile look like from a data
perspective?

The main purpose of the project was to turn my GitHub activity into a
data analytics problem and build an end-to-end workflow using:

GitHub API → Python → Data Preparation → SQLite / CSV → Power BI

Tools & Technologies

Python

Pandas

Requests

GitHub REST API

SQLite

SQL

Power BI
