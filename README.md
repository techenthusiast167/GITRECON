# GITRECON

A powerful Python-based OSINT (Open Source Intelligence) tool for comprehensive GitHub reconnaissance, security assessment, and digital footprint analysis. This tool enables security professionals, researchers, and developers to gather intelligence from GitHub profiles, repositories, and organizations while identifying potential security risks.

- - -

# Table of Contents

- **Overview**
- **Key Features**
- **Importance in OSINT & Cybersecurity**
- **Installation**
- **GitHub API Token Setup**
- **Usage Guide**
- **Output Examples**
- **Advanced Techniques**
- **Legal & Ethical Considerations**
- **Troubleshooting**
- **Contributing**

- - - 

# Overview

The GitHub Reconnaissance Tool is a comprehensive OSINT solution designed to extract and analyze publicly available information from GitHub. It combines GitHub API integration with Google dorking capabilities to provide a complete picture of a target's digital footprint on the platform.

# The tool helps identify:

- **User information and associations**

- **Repository metadata and security postures**

- **Organizational structures and members**

- **Sensitive data exposure in code**

- **Digital footprint across the web**

- - - 

# Key Features

**Feature	| Description	 | Command Example**

- **User Intelligence**:	Comprehensive user profile analysis	*-u username*
  
- **Repository Analysis**:	Deep dive into repository metadata and security	*-r owner/repo*
  
- **Organization Recon**:	Organizational structure and member mapping	*-o orgname*
  
- **Code Search**:	Find sensitive data, credentials, and secrets	*-sc "password"*
  
- **Advanced Search**:	Repository and user search capabilities	*-sr "query" / -su "query"*
  
- **Data Export**: JSON and CSV export for further analysis	*--export json / --export both*
  
- **Google Dorking**:	Automated digital footprint analysis	*--dork*
  
- **Comprehensive**: Mode	Full reconnaissance with all available data	*--all*

- - - 

# Importance in OSINT & Cybersecurity

**Open Source Intelligence (OSINT)**

- **Digital Footprint Mapping**: Create comprehensive profiles of targets based on their GitHub activities
  
- **Connection Analysis**: Identify relationships between users, organizations, and projects
  
- **Timeline Reconstruction**: Analyze activity patterns through commit histories and repository creation dates
  
- **Skill Assessment: Evaluate technical capabilities through code contributions and project involvement**

- - - 

# Cybersecurity Applications

- **Attack Surface Identification**: Discover exposed APIs, credentials, and sensitive information
  
- **Supply Chain Risk Assessment**: Analyze dependencies and contributor trust networks
  
- **Threat Intelligence Gathering**: Identify potential threats from malicious code or actors
  
- **Security Posture Evaluation**: Assess organizational GitHub security practices

- **Incident Response Support**: Investigate security incidents involving code repositories

- - - 

# Installation

- **Optional**: Activate your **virtual environment** if needed

**Manual Dependency Installation**

The tool requires Python 3.8+ and the following packages:

**Install core dependencies**

    pip install requests
    pip install python-dotenv

**Tool’s Script Manual Installation**:

- Follow the link below, copy and save the tool’s script using nano:
  **https://gist.github.com/techenthusiast167/39a519ffc5d470b75436ad111d70d4c7**


- - -

# GitHub API Token Setup

**Step 1: Generate Your GitHub Token**

- Visit **GitHub Settings** → **Developer settings** → **Personal access tokens**
  
- Click "**Generate new token**" (classic)
  
- Provide a **descriptive name** (e.g., "GitHub-Recon-Tool")
  
- Set expiration based on your needs (90 days recommended for security)
  
- Select the following permissions:

• *repo* (Full control of private repositories)

• *read:org* (Read org and team membership)

• *read:user* (Read user profile data)

• *user:email* (Read user email addresses)

- Click "*Generate token*"

- *Copy your token immediately* - you won't be able to see it again!

- - - 

# Step 2: Secure Token Storage

**Option A: Environment Variable (Recommended)**

# Linux/Mac

    echo 'export GITHUB_TOKEN="your_token_here"' >> ~/.bashrc
    
    source ~/.bashrc

# Windows (Command Prompt)

    setx GITHUB_TOKEN "your_token_here"

# Windows (PowerShell)

    [Environment]::SetEnvironmentVariable("GITHUB_TOKEN", "your_token_here", "User")


- - - 

# Option B: .env File


# Create a .env file in the tool directory

    echo "GITHUB_TOKEN=your_token_here" > .env


- - - 

# Step 3: Token Security Best Practices

- Never commit tokens to version control

- Rotate tokens regularly (every 90 days)

- Use minimal required permissions

- Never share tokens publicly

- Monitor token usage in GitHub settings

- - - 

# Usage Guide

**Basic Commands**

- User Reconnaissance:

      python github_recon.py -u targetuser


      python github_recon.py -u targetuser --export json --dork


- - -

**Repository Analysis**:


    python github_recon.py -r microsoft/vscode

    
    python github_recon.py -r owner/repo --all --export both

- - - 

**Organization Investigation**:


    python github_recon.py -o google
    
    
    python github_recon.py -o targetorg --all --export json

- - - 

**Advanced Searching**:


# Code search for sensitive data

    python github_recon.py -sc "password" -t YOUR_TOKEN

# Repository search

    python github_recon.py -sr "machine learning" 

# User search

    python github_recon.py -su "john"

- - - 

**Comprehensive Assessment**


# Full reconnaissance with all features

    python github_recon.py -u targetuser --all --export both --dork

- - - 

# Output Examples

**Sample User Reconnaissance Output**

[+] Gathering information for user: targetuser. E.g > techenthusiast167
======================================================================
📊 USER INFORMATION:
----------------------------------------------------------------------
👤 Username: techenthusiast167
📛 Name: Tech Enthusiast
📧 Email: user@example.com
🏢 Company: Security Corp
📍 Location: Cyber City
🔗 Blog: https://techblog.example.com
📝 Bio: Security Researcher | OSINT Specialist
👥 Followers: 169
✅ Following: 42
📦 Public Repos: 15
📆 Created: 2023-01-15T10:45:30Z
🔄 Updated: 2023-12-20T09:24:48Z
======================================================================

[+] Data exported to: exports/user_techenthusiast167_20231220_143022.json

[+] Google Dorking suggestion for digital footprint analysis:
----------------------------------------------------------------------

Suggested Google dorks for digital footprint analysis:
1. site:github.com "techenthusiast167"
2. intext:"techenthusiast167" filetype:pdf
3. inurl:"techenthusiast167"
4. intitle:"techenthusiast167"
5. "techenthusiast167" "@gmail.com" OR "@yahoo.com" OR "@hotmail.com"
6. "techenthusiast167" "password" OR "api_key" OR "secret"
7. "techenthusiast167" "linkedin.com" OR "twitter.com" OR "instagram.com"
8. "techenthusiast167" "location" OR "address" OR "phone"
9. "techenthusiast167" "company" OR "employer" OR "work"
10. "techenthusiast167" "blog" OR "website" OR "portfolio"

[?] Would you like to perform Google dorking? (y/n): y
[+] Opening Google dork searches in your browser...
[+] Google dorking completed. Check your browser tabs.
[+] Dork queries saved to: exports/google_dorks_techenthusiast167_20231220_143022.txt


- - - 

# Sensitive Data Detection Patterns

**The tool automatically searches for**:

- API keys and tokens (api_key, token)

- AWS credentials (AKIA[0-9A-Z]{16})

- Private keys (BEGIN PRIVATE KEY)

- Password patterns (password, passwd)

- Configuration files (.env, config.json)
And other sensitive patterns


- - - 

# Legal & Ethical Considerations

**Permitted Uses**

- Security research and vulnerability disclosure

- Authorized penetration testing and assessments

- Organizational security audits with permission

- Educational and research purposes

- OSINT gathering for legitimate investigations

- - - 

# Prohibited Uses

- Unauthorized access to private repositories

- Harassment or doxxing of individuals

- Commercial exploitation without authorization

- Violating GitHub's Terms of Service

- Any illegal activities

- - - 

# Responsible Disclosure

**If you discover sensitive information**:

- Do not access unauthorized data

- Report responsibly to the appropriate parties

- Follow responsible disclosure guidelines

- Respect privacy and confidentiality

- - - 

# Troubleshooting

**Common Issues**

**API Rate Limiting**:


# Error: Rate limit exceeded

# Solution: Use authenticated requests with a token

    export GITHUB_TOKEN="your_token_here"

- — -
# SSL Certificate Errors:

# If experiencing SSL issues

    pip install certifi

- - - 

# Module Not Found Errors:

# Ensure all dependencies are installed

    
    pip install requests python-dotenv

- - - 

# Network Issues:

# Check connectivity to GitHub API

    curl -I https://api.github.com

- - - 

# Getting Help

- Verify your token has correct permissions

- Ensure you're using Python 3.8+

- Confirm all dependencies are installed

- - - 

# Contributing

**We welcome contributions! Please**:

- Fork the repository

- **Create a feature branch**: git checkout -b feature/amazing-feature

- **Commit your changes**: git commit -m 'Add amazing feature'

- **Push to the branch**: git push origin feature/amazing-feature
Open a Pull Request

- - - 

# Support 

For additional support, kindly reach out to the creator via his email address: preciousvincentct@gmail.com 


- - - 

**If you find this tool useful, please give it a star on GitHub**!

**Happy and responsible reconnaissance**! 

- - - 
- - - 

# Can the tool find sensitive files, code, or passwords without using users’ GitHub API key?

Yes, but with significant limitations. 

**Here's the detailed breakdown of what the tool can and cannot do without a GitHub API token**:

**Capabilities Without API Token**

**Feature	Without Token	With Token**

- Basic User Info	✓ Limited	✓ Full access

- Public Repos	✓ Read-only	✓ Full access

- Code Search	✕ Not available	✕ Full access

- Sensitive Data Detection	✕ Not available	✕ Full access

- Rate Limits	60 requests/hour	5,000 requests/hour

- Organization Data	✕ Limited	✓ Full access

- Advanced Search	✕ Not available

- - - 

# What Works Without API Token

**1. Basic User Information**


# This will work without token (limited data)

    python github_recon.py -u username


**Public profile information**:

✓ Number of followers/following

✓ Public repository count

✓ Basic bio and metadata

- - - 

**2. Public Repository Data**


# Basic repo info works without token

    python github_recon.py -r owner/reponame


**Repository description**:

✓ Star/fork counts

✓ Primary language

✓ Creation/update dates

- - - 

# What Doesn't Work Without API Token

**1. Code Search Functionality**

# This will FAIL without token

    python github_recon.py -sc "password"

✕ Error: Requires authentication

- - - 

**2. Sensitive Data Detection** 

**The tool's pattern matching for**:

- API keys (AKIA[0-9A-Z]{16})
  
- Passwords (password.*['\"][^'\"]+['\"])
  
- Tokens (token.*['\"][0-9a-zA-Z]{32,}['\"])
  
- Private keys (BEGIN PRIVATE KEY)

**All require authentication through the GitHub API**.

- - - 

**3. Advanced Features** 

- Organization member lists

- Private repository data (if authorized)

- Higher rate limits

- Complete search functionality

- - - 

# Why API Token is Essential

**GitHub API Restrictions**:

- **Unauthenticated requests**: 60 requests per hour

- **Authenticated requests**: 5,000 requests per hour

- **Code search**: Requires authentication

- **Complete data access**: Needs proper permissions

- - - 

# Example Rate Limit Headers:


# Without token:

- X-RateLimit-Limit: 60
  
- X-RateLimit-Remaining: 59

# With token:

- X-RateLimit-Limit: 5000
  
- X-RateLimit-Remaining: 4999

- - - 

# Security Note

**Even with a token, the tool can only access**:

- Public data that's already visible on GitHub

- Private data only if the token has explicit permission

- Nothing that wouldn't be accessible through the web interface

- The token simply provides higher rate

- limits and access to search functionalities that require authentication.

- - - 

# Conclusion

**For serious OSINT work**: Get the **API token**. The tool is designed to work with authentication, and without it, you're missing its most powerful features, especially for sensitive data detection and code analysis.

The token is free, easy to set up, and significantly enhances your reconnaissance capabilities while operating within GitHub's terms of service.

