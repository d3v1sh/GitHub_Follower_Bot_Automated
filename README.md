![Alt text](gh_bot.png)

# GitHub Follower Bot Automated

Welcome to the **GitHub Follower Bot Automated** repository! This project is designed to help you automatically follow your GitHub followers, keeping your network growing and engaged with minimal effort.

:raised_hand::raised_hand::raised_hand:**You Follow Me** ---> **My Bot Follows you Back! Let's grow Together!**:raised_hand::raised_hand::metal:

:star::star::star::star::star: ---> Star the Repo!

## 📝 Usage

The bot will fetch your list of followers and automatically follow any users that are not already followed.
A log of followed users is maintained in the `followers.txt` file.
The bot will continue to run until all followers have been processed.

Additionally, the `check_all_followers.py` script allows you to monitor how many followers you have and how many you can follow based on your current GitHub API rate limits.

The bot can be run in two ways:
1. **[Manually](#run-the-bot-manually)**: You can run the bot manually on your local machine.
2. **[Automatically with GitHub Actions](#github-actions-workflow-setup)**: Set up the bot to run automatically on a schedule using GitHub Actions.

## Project Structure

```plaintext
GitHub_Follower_Bot_Automated/
│
├── bot.py                    # Main script for the bot.
├── check_all_followers.py     # Script to check total followers and available follows.
├── followers.txt              # File where followed users are logged.
├── follower_counter.txt       # Total number of users followed across all runs.
├── requirements.txt           # Python dependencies.
├── .env                       # Environment variables (must be created).
├── bot.log                    # Log file for bot.py activities.
├── check_all_followers.log    # Log file for check_all_followers.py activities.
├── LICENSE                    # Project licensing information.
└── README.md                  # This readme file.
```

## 🚀 Features

- **Automated Follower Management:** Automatically follows users who follow you on GitHub.
- **User-Friendly:** Easy to set up and run, even for those with minimal technical knowledge.
- **Error Handling:** Built-in error handling ensures smooth operation and reliability.
- **Logging:** Comprehensive logs for tracking bot activity and performance.
- **Persistent Tracking:** Maintains a persistent follower counter across multiple runs.
- **Rate Limit Awareness:** Monitors GitHub API rate limits to prevent exceeding them.

## 🛠️ Setup & Installation To Run the Bot Manually on Local Server
### Run the Bot Manually

### 1. Clone the Repository
Clone this repository to your local machine:
```bash
git clone https://github.com/d3v1sh/Follozy-v2.git
cd Follozy-v2
```

### 2. Install Dependencies
Install the required Python packages using pip:
```bash
pip install -r requirements.txt
```

### 3. Configure Environment Variables
Create a .env file in the project root and add your GitHub username and Personal Access Token:
```bash
GITHUB_USER=your_github_username
PERSONAL_GITHUB_TOKEN=your_personal_access_token
```
**Make sure you do not commit this file to the repository as it contains sensitive information. Create .gitignore file and add .env to it.**

### 4. Run the Bot
Run the bot using the following command:
```bash
python follower_bot.py
```

## 🛠️ Setup & Installation To Run the Bot every 10 minutes with GitHub Actions (Automatically)
### GitHub Actions Workflow Setup
To set up the bot to run automatically on a schedule using GitHub Actions, follow these steps:

1. **Creating a Personal Access Token (PAT):**
   - Go to GitHub Settings and navigate to "Developer settings" > "Personal access tokens".
   - Generate a new token with the required scopes.
   - Save the token securely.

2. **Storing the PAT as a GitHub Secret:**
   - Navigate to your repository's "Settings" > "Secrets and variables" > "Actions".
   - Add a new secret named `PERSONAL_GITHUB_TOKEN` and paste the token.

3. **Updating the GitHub Actions Workflow File:**
   - Reference the token in your workflow file:
     ```yaml
     env:
       GITHUB_TOKEN: ${{ secrets.PERSONAL_GITHUB_TOKEN }}
     ```
   - Adjust the cron schedule as needed:
     ```yaml
     schedule:
       - cron: '0 0 * * *'
     ```

4. **Granting Workflow Permissions:**
   - Add the necessary permissions to your workflow file:
     ```yaml
     permissions:
       contents: write
       issues: write
       pull-requests: write
       actions: write
     ```

5. **Monitoring the Workflow:**
   - Monitor the workflow runs in the "Actions" tab of your GitHub repository.

## 🤖 Bot Configuration

### Environment Variables
- `GITHUB_USER`: Your GitHub username.
- `PERSONAL_GITHUB_TOKEN`: Your GitHub Personal Access Token for API access.

### Optional Features
Additional features can be implemented as needed. Check the Issues and Discussions sections for ideas and contributions.

## 📈 Contributions

Contributions are welcome! Feel free to submit a pull request or open an issue for suggestions, bug reports, or feature requests.

### To Contribute:
1. Fork the repository.
2. Create a new branch (`git checkout -b dev`).
3. Make your changes.
4. Commit your changes (`git commit -m 'Add some feature'`).
5. Push to the branch (`git push origin dev`).
6. Open a pull request.

## 🔒 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## 📞 Support

For any questions or issues, please feel free to reach out via GitHub Issues or Discussions.




