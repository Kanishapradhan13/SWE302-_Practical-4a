# Practical 4a: Setting up SAST with SonarCloud in GitHub Actions

## Overview

This practical demonstrates how to integrate SonarCloud, a cloud-based Static Application Security Testing (SAST) tool, with GitHub Actions for automated code quality and security analysis in a Java/Maven project. The exercise covers SonarCloud setup, GitHub integration, workflow automation, security report interpretation, and continuous monitoring.

## Objectives

- Understand the principles of SAST and SonarCloud
- Set up SonarCloud and connect it to a GitHub repository
- Automate security scanning using GitHub Actions
- Interpret SonarCloud security reports and quality gates
- Implement continuous monitoring for code security

## Learning Outcomes

By completing this practical, you will be able to:

- Explain the role of SAST in secure software development
- Configure SonarCloud for source code analysis
- Integrate SonarCloud scans into CI/CD pipelines using GitHub Actions
- Analyze and remediate security vulnerabilities and hotspots
- Set up and enforce quality gates for security
- Monitor code security trends over time

## Steps Involved

### 1. SonarCloud Account and Project Setup
- Created a SonarCloud account and linked it to GitHub
- Imported the organization and selected the `cicd-demo` repository
- Generated a SonarCloud API token and added it to GitHub Secrets as `SONAR_TOKEN`
- Added organization and project keys to GitHub Secrets

### 2. Configuration Files
- Created `sonar-project.properties` with project, organization, source, and test paths
- Updated `pom.xml` to include SonarCloud Maven plugin and JaCoCo for coverage
- Created `.github/workflows/sonarcloud.yml` for automated analysis on push and PR

### 3. Running SonarCloud Analysis
- Triggered GitHub Actions workflow on code push
- Verified successful workflow execution and SonarCloud dashboard update

### 4. Security Report Interpretation
- Reviewed SonarCloud dashboard for vulnerabilities and security hotspots
- Analyzed severity, location, and recommendations for each issue

### 5. Quality Gate Configuration
- Configured a custom quality gate named "Security-First" in SonarCloud
- Enforced security rating A and zero new vulnerabilities on new code
- Updated workflow to fail on quality gate failure

### 6. Continuous Monitoring
- Implemented scheduled weekly scans using GitHub Actions
- Monitored security metrics and trends via SonarCloud dashboard

## Conclusions

Integrating SonarCloud with GitHub Actions enables automated, continuous security and quality analysis for source code. Quality gates enforce security standards, and regular scans help identify and remediate vulnerabilities early. This approach supports a security-first development culture and complements dependency scanning tools like Snyk for comprehensive coverage.


### Security Issues Identified 

1. **SQL Injection Vulnerability**
	- **Severity:** Critical
	- **Description:** User input is concatenated directly into an SQL query, risking SQL injection.
	- **Recommendation:** Refactor to use prepared statements or parameterized queries.

2. **Hard-coded Credentials**
	- **Severity:** Major
	- **Description:** Database password is hard-coded in the source code.
	- **Recommendation:** Use environment variables or secret management solutions.

