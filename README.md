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

**Manual Dependency Installation**

The tool requires Python 3.8+ and the following packages:

*Install core dependencies*

    pip install requests
    pip install python-dotenv

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



