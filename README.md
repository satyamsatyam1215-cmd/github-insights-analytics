# GitHub Insights Analytics

A Python and Power BI project that connects to the GitHub REST API, collects GitHub profile, repository, traffic, and language data, and turns it into structured datasets for analysis.

The project automates the process of collecting GitHub data, preparing it with Pandas, storing it in SQLite and CSV files, and analysing it through Power BI.

---

## Workflow

```text
GitHub API
     ↓
Python (Requests)
     ↓
Pandas
     ↓
Data Cleaning
     ↓
SQLite / CSV
     ↓
Power BI
```

---

## Tech Stack

- **Python:** Pandas, Requests
- **API:** GitHub REST API
- **Database:** SQLite
- **Querying:** SQL
- **Visualization:** Power BI

---

## Project Outputs

Running the Jupyter Notebook generates the following files:

| File | Description |
|---|---|
| `df_user.csv` | GitHub profile-level information such as followers, following, and public repositories |
| `df_repositories.csv` | Repository-level information and metadata |
| `df_traffic.csv` | Repository traffic including views, unique visitors, clones, and unique cloners |
| `df_languages.csv` | Programming languages and byte usage across repositories |
| `github_analytics.db` | SQLite database containing `user`, `repositories`, `traffic`, and `languages` tables |

---

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/satyamsatyam1215-cmd/github-insights-analytics.git
cd github-insights-analytics
```

### 2. Install Required Libraries

```bash
pip install requests pandas
```

### 3. Create a GitHub Personal Access Token

This project uses a GitHub Personal Access Token to access GitHub API data.

To create one:

1. Open GitHub.
2. Go to **Settings**.
3. Open **Developer settings**.
4. Go to **Personal access tokens → Fine-grained tokens**.
5. Click **Generate new token**.
6. Select your GitHub account as the resource owner.
7. Select the repositories you want to analyse.
8. Provide the required read permissions.
9. Generate the token and copy it.

### 4. Configure the Notebook

Open:

```text
Pyhton Code.ipynb
```

Update the first cell:

```python
GITHUB_USERNAME = "your-github-username"
GITHUB_TOKEN = "YOUR_TOKEN_HERE"
```

For example:

```python
GITHUB_USERNAME = "satyamsatyam1215-cmd"
GITHUB_TOKEN = "YOUR_TOKEN_HERE"
```

> **Important:** Never upload your actual GitHub token to a public repository. Keep it private and use a new token if an existing one is exposed.

### 5. Run the Notebook

Run the notebook cells from top to bottom.

The notebook will:

1. Connect to the GitHub REST API.
2. Collect profile information.
3. Collect repository information.
4. Collect repository traffic.
5. Collect programming-language information.
6. Create Pandas DataFrames.
7. Clean unnecessary fields.
8. Store the data in SQLite.
9. Export the final datasets as CSV files.

---

## Data Collected

### User Data

The `df_user.csv` file contains profile-level information used to understand the GitHub account.

### Repository Data

The `df_repositories.csv` file contains information about the repositories owned by the account.

### Traffic Data

The `df_traffic.csv` file contains repository traffic data such as:

- Views
- Unique visitors
- Clones
- Unique cloners
- Date
- Repository name

### Language Data

The `df_languages.csv` file contains:

- Repository name
- Programming language
- Byte usage

This can be used to understand the programming languages used across the repositories.

---

## What the Python Code Does

The notebook uses the GitHub REST API to collect the required data.

The collected API responses are converted into four Pandas DataFrames:

```python
df_user
df_repositories
df_traffic
df_languages
```

The data is then cleaned by removing unnecessary API fields.

The cleaned DataFrames are stored in a local SQLite database:

```text
github_analytics.db
```

The database contains:

```text
user
repositories
traffic
languages
```

The same DataFrames are also exported as CSV files for further analysis.

---

## Power BI Report

The collected data is used to create a Power BI dashboard for analysing GitHub activity.

The report provides an overview of:

### Profile Overview

- GitHub ID
- Followers
- Following
- Public repositories
- Account age
- Repositories per year

### Traffic Overview

- Total views
- Total clones
- Unique visitors
- Unique cloners
- Average daily views
- Peak daily views
- Active traffic days
- Repositories with traffic

### Traffic Trend

The report shows GitHub views and clones over time.

### Repository Performance

Repositories can be compared using:

- Views
- Visitors
- Clones
- Interactions
- Activity

### Top Repositories

The dashboard identifies repositories receiving the highest number of views and allows repository performance to be compared.

---

## Why I Built This

I built this project because I wanted to understand my GitHub account through data.

GitHub provides useful information about repositories, traffic, and profile activity, but I wanted to bring that information together instead of checking different sections manually.

The project helps me analyse questions such as:

- Which repositories receive the most views?
- Which repositories get more traffic?
- How many visitors and clones do my repositories receive?
- How does repository traffic change over time?
- Which programming languages are used across my repositories?
- What does my GitHub activity look like from a data perspective?

The main idea was simple: **turn my GitHub activity into a data analytics project.**

The final workflow is:

```text
GitHub API → Python → Data Cleaning → SQLite / CSV → Power BI
```
