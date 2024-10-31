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