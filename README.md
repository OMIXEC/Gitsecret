# Gitsecret
A Python script to scan GitHub repositories, local files, or URLs for potentially sensitive information.  This tool helps developers and security professionals identify secrets accidentally committed to public repositories or shared files.

## Features

* **GitHub Scanning:** Search public GitHub repositories for files matching sensitive patterns (uses GitHub API for efficiency). Supports recursive subdirectory searching.
* **Local File Scanning:** Scan local files for sensitive information.
* **URL Scanning:** Scan the content of a URL for sensitive information.
* **Self-Scan Mode:**  Scan your own public GitHub repositories to find and remediate any exposed secrets.
* **Customizable Patterns:** Easily configure the regular expression patterns used to identify sensitive information.
* **Threading:** Uses multithreading for faster GitHub repository scanning.
* **User-Friendly Output:** Provides clear and informative output, indicating the location of any potential secrets found.
* **Interactive Navigation:**  Offers options to scan multiple targets and switch between scan types.
* **Robust Error Handling:** Handles network errors, invalid inputs, and other potential issues gracefully.


## Requirements

See `requirements.txt`

## Installation

**Clone the Repository:**

   ```bash
   git clone https://github.com/YOUR_USERNAME/gitsecret.git 
   cd gitsecret

Install Dependencies:
pip install -r requirements.txt

**Usage:**
python gitsecret.py -u <username>       # Scan a GitHub user
python gitsecret.py -f <filepath>       # Scan a local file
python gitsecret.py -l <url>            # Scan a URL
python gitsecret.py -s                  # Perform a self-scan (your repositories)

*Configuration:*
Sensitive File Patterns (Advanced)
You can customize the regular expression patterns used to detect sensitive information by modifying the patterns list in the gitsecret.py script. The patterns are defined as raw strings (e.g., r"\.env$").

GitHub API Rate Limiting
The GitHub API has rate limits. If you encounter rate limiting issues, you have several options:

Use a GitHub Personal Access Token (Recommended): Create a personal access token with the "repo" scope on GitHub and set it as an environment variable named GITHUB_TOKEN. The script will automatically use this token to authenticate and increase your rate limit. Instructions to create a PAT

Reduce the Number of Concurrent Threads: Modify the max_workers argument in the ThreadPoolExecutor to decrease the number of concurrent requests.

Example .env file (if used)
If you use a .env file to store your GITHUB_TOKEN, it should have the following format:

GITHUB_TOKEN=your_actual_github_pat
Use code with caution.
Make sure to add .env to your .gitignore file to prevent it from being accidentally committed to your repository.

*Disclaimer*
This tool is intended for security testing and educational purposes only. It should not be used without explicit permission from the target. Unauthorized access or scanning of computer systems or networks is illegal. The developers of this tool are not responsible for any misuse or illegal activities performed using this script.
