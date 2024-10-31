# Sydney-100

# GitHub User and Repository Data Collection

- This project scrapes user data from GitHub using its API, targeting users located in Sydney with over 100 followers. The process involves making multiple API requests to gather essential user information, which is then saved into CSV files for further analysis and insights into the developer community.

- One surprising finding from the data analysis is that a considerable number of users do not list a company, suggesting that many developers may be independent, freelance, or simply choose not to disclose their affiliations. This anonymity highlights a diverse range of developer experiences within the GitHub community.

- To enhance the data collection process, developers should implement robust error handling and validation techniques. This ensures the integrity and completeness of the dataset while minimizing the chances of missing or incorrect information. Additionally, consider expanding the data fields collected for more comprehensive insights into user profiles and activities.



## Project Overview
This project focuses on scraping user and repository data from GitHub to analyze the profiles of developers located in Sydney. The information collected can provide valuable insights into developer activity and company engagement within the region.

## How It Works
1. **User Data Collection**: The script uses the GitHub API to fetch users based in Sydney with more than 100 followers. It retrieves key details such as their login, name, company, location, email, bio, public repositories, followers, and account creation date.
2. **Company Name Validation**: The collected company names are cleaned by removing whitespace, stripping leading '@' symbols, and converting to uppercase for consistency.
3. **Repository Data Collection**: For each user, the script fetches public repositories, capturing attributes like the repository's full name, creation date, star count, language, and license information.

## Data Description
The project generates two CSV files:
- **users.csv**: Contains detailed information about GitHub users.
- **repositories.csv**: Includes data about the public repositories owned by the scraped users.

### Sample Data Fields
#### users.csv
The collected data includes:
- **Login**: The GitHub username.
- **Name**: The real name of the user (if provided).
- **Company**: The organization the user works for, cleaned of leading `@` symbols and converted to uppercase.
- **Location**: The geographical location of the user.
- **Email**: Contact email (if publicly available).
- **Hireable**: Indicates if the user is open to job offers.
- **Bio**: A brief description of the user.
- **Public Repositories**: The number of public repositories owned.
- **Followers**: The count of followers.
- **Following**: The count of accounts the user follows.
- **Created At**: The date the user account was created.

### `repositories.csv`
This file contains detailed information about the public repositories for each user, including:
- **Login**: The user's GitHub login.
- **Full Name**: The full name of the repository.
- **Created At**: The date the repository was created.
- **Stargazers Count**: The number of stars the repository has received.
- **Watchers Count**: The number of watchers of the repository.
- **Language**: The primary programming language used in the repository.
- **Has Projects**: Indicates if the repository has project boards.
- **Has Wiki**: Indicates if the repository has a wiki.
- **License Name**: The type of license the repository uses (if applicable).

## Usage
1. Ensure you have Python and the required packages installed (e.g., `requests`, `pandas`).
2. Replace the GitHub token in the code with your personal access token for authentication.
3. Run the script to fetch user and repository data, which will be saved to `users.csv` and `repositories.csv`.

## How to Download Files
To download the CSV files after running the scripts in Google Colab, use the following code:
```python
from google.colab import files

# Download users.csv
files.download("users.csv")

# Download repositories.csv
files.download("repositories.csv")
