# Tool to Export GitHub Commits to CSV

## Setup

Install Python 3+

Environemnt:

1. Create a virtual environment: `python -m venv venv`
2. Activate virtualenv: `.\venv\Scripts\activate` (Windows), `source venv/bin/activate` (Linux)
3. Install packages from requirements.txt: `pip install -r requirements.txt`
4. Copy `.env.example` to `.env` and populate variables
5. Retrieve a fine-grained personal access token from GitHub:
   - Go to GitHub -> Settings -> Developer settings -> Personal access tokens -> Fine-grained tokens
   - Select an organization in the `Resource owner` list. If the organization isn't listed, allow fine-grained personal access token in [organization policy](https://docs.github.com/en/organizations/managing-programmatic-access-to-your-organization/setting-a-personal-access-token-policy-for-your-organization).
   - Generate a new token with `Contents` `Read-only` access
   - Copy the token and paste it in `.env` as `GITHUB_ACCESS_TOKEN`

## Run

Open `github_commits_to_csv` notebook and run all cells.

## Sniff HTTP Requests

### Windows

Use [2. Old Solution (Not recommended)](https://docs.proxyman.io/debug-devices/python#2.-old-solution-not-recommended).

1. Download cert from Proxyman: Certificate -> Export -> Root Certificate as PEM...
2. Save that file to certs folder
3. Inside venv: `python proxyman.py add`
4. Paste relative path to cert file

To disable proxyman proxy:

1. Inside venv: `python proxyman.py remove`

### Mac

Use [1. New Automatic Solution (v4.7.0 or later)](https://docs.proxyman.io/debug-devices/python#1.-new-automatic-solution-v4.7.0-or-later).

When new Terminal launches, open vscode from there:

```
cd projects/examind-essay
code .
```
