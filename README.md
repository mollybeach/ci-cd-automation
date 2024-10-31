# CI/CD Automation Project

This project demonstrates the setup of a CI/CD pipeline for a Node.js application using Jenkins and GitHub Actions.

## Features
- Jenkins pipeline for CI/CD automation
- GitHub Actions integration for testing and deployment
- Webhook setup for automatic build triggers

## Tech Stack
- Node.js
- Jenkins
- GitHub Actions
- Jest for testing

## Setup
1. Clone the repository
2. Install dependencies: `npm install`
3. Configure Jenkins and GitHub Actions for the repository
4. Push code to trigger CI/CD pipeline

## Tests
- Run tests locally: `npm test`

## CI/CD Pipeline Setup

### GitHub Actions Configuration
1. Create `.github/workflows/ci.yml` for automated testing
2. Configure GitHub repository secrets if needed
3. Enable GitHub Actions in repository settings

### Jenkins Setup
1. Install required Jenkins plugins:
   - GitHub plugin
   - GitHub Integration Plugin
   - Pipeline plugin
   - NodeJS plugin
2. Create new Jenkins pipeline job
3. Configure webhook: `http://<jenkins-server-url>/github-webhook/`
4. Set up environment variables in Jenkins

### Deployment
1. Configure deployment credentials in Jenkins
2. Update Jenkinsfile with deployment steps
3. Push changes to trigger the pipeline

## Project Structure

```
ci-cd-automation/
├── .git/
├── .github/
│   └── workflows/
│   │   └── ci.yml
├── node_modules/
├── src/
│   └── app.js
├── tests/
│   └── app.test.js
├── .eslintrc.json
├── .gitignore
├── package-lock.json
├── package.json
└── README.md
```

## What is Jenkins?

Jenkins is an open-source automation server that helps developers build, test, and deploy their applications. Think of it as an automated assistant that handles repetitive tasks in the development process.

### Key Features
- **Automation**: Automatically builds and tests code when changes are made
- **Integration**: Works with many tools and services (GitHub, GitLab, etc.)
- **Pipeline Management**: Creates automated workflows (Code → Test → Build → Deploy)

### Benefits
- **Time Saving**: Automates repetitive tasks and speeds up development cycles
- **Quality Control**: Ensures consistent testing and early bug detection
- **Reliability**: Provides standardized deployment process with reduced human error

# Jenkins Setup Guide

## Access Jenkins
```bash
http://localhost:8080/
```

## 1. Install Required Plugins
1. Navigate to `Manage Jenkins` > `Plugins` > `Available`
2. Search and install the following plugins:
   - NodeJS Plugin
   - GitHub Plugin
   - Pipeline
   - Git plugin
3. Click "Install without restart"

## 2. Configure NodeJS
1. Navigate to `Manage Jenkins` > `Tools` > `Global Tool Configuration`
2. Under NodeJS section:
   - Click "Add NodeJS"
   - Name: `Node-18` (or `Node-20`)
   - Version: Select `18.x` (LTS) or `20.x` (Latest LTS)
3. Click "Save"

## 3. Create Pipeline
1. Click "New Item"
2. Enter project name: `ci-cd-automation`
3. Select "Pipeline"
4. Click "OK"

## 4. Configure Pipeline
Navigate through each section and configure as follows:

### General Settings
- ✓ Check "GitHub project"
- Enter your GitHub repository URL

### Build Triggers
- ✓ Check "GitHub hook trigger for GITScm polling"

### Pipeline Settings
- Definition: `Pipeline script from SCM`
- SCM: `Git`
- Repository URL: `[Your GitHub Repository URL]`
- Branch Specifier: `*/main`
- Script Path: `Jenkinsfile`

### Save Configuration
Click "Save" to complete setup

## Verification
After saving, your pipeline should be ready to:
- Detect changes from GitHub
- Run automated builds
- Execute tests
- Deploy (if configured)