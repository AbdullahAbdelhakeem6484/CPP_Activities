# Development Branch Setup Guide

Welcome to the Development Branch Setup Guide! This document outlines the steps for each team member to create their own development branch, along with an automated script to streamline the process.

## Naming Convention
Each developer should create their branch following this naming convention:
- `username_dev` (e.g., `abdullah_dev`, `ramadan_dev`)

## Steps to Create Your Development Branch

1. **Clone the Repository**
   Make sure you have the main repository cloned. If you haven't cloned it yet, use:
   ```bash
   git clone https://github.com/your-repo-url.git
   cd your-repo-name


2.  **Push Your Development Branch to Remote**
Push your new branch to the remote repository:

```bash
git push origin username_dev
```
   
3.  **Push Your Development Branch to Remote**
Push your new branch to the remote repository:
```bash
git push origin username_dev
```

4. **Merge Changes from Other Development Branches (if needed)**
If you need to incorporate changes from another developer's branch, use:
```bash
git checkout your_branch
git merge username_dev
```



**Automated Script**
To simplify the process of creating your development branch, you can use the following script. This script will prompt you for your username and automatically create and push your development branch.

Bash Script: create_dev_branch.sh

```bash
#!/bin/bash

# Check if a username is provided
if [ -z "$1" ]; then
  echo "Usage: ./create_dev_branch.sh <username>"
  exit 1
fi

USERNAME="$1"
BRANCH_NAME="${USERNAME}_dev"

# Clone the repository if not already cloned
if [ ! -d "your-repo-name" ]; then
  echo "Cloning the repository..."
  git clone https://github.com/your-repo-url.git
  cd your-repo-name || exit
else
  cd your-repo-name || exit
fi

# Create and switch to the new branch
git checkout -b "$BRANCH_NAME"

# Push the new branch to remote
git push origin "$BRANCH_NAME"

echo "Development branch '$BRANCH_NAME' created and pushed successfully!"
```


Usage
1. Save the script as create_dev_branch.sh.
2. Make it executable:
```bash
chmod +x create_dev_branch.sh
```
3.Run the script with your username:
```bash
./create_dev_branch.sh your_username
```
