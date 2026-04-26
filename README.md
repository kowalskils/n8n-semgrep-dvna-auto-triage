# n8n-semgrep-dvna-auto-triage

> Automated DevSecOps vulnerability triage and remediation orchestration built with n8n, GitHub Actions, Semgrep SAST and GitHub Issues.

<p align="center">
  <a href="https://youtu.be/ONs2RsDuWzU">▶ Watch Live Demo</a>
</p>

---

## Overview

Modern AppSec teams often struggle with the repetitive operational burden of manually reviewing SAST findings, classifying vulnerability severity, and opening remediation tickets for engineering teams.

This project demonstrates an automated DevSecOps orchestration pipeline where Semgrep scan results are processed by an n8n workflow and transformed into actionable GitHub remediation issues based on business risk.

The automation performs:

- Automated ingestion of Semgrep SAST findings from GitHub Actions
- Parsing and normalization of vulnerability metadata
- Severity-based risk triage logic
- Individual remediation issue creation for Critical/High findings
- Consolidated backlog issue creation for Medium/Low findings
- Automatic remediation labeling and security governance tracking

---

## Architecture

<p align="center">
  <img src="public/assets/architecture.png" alt="architecture" width="90%">
</p>

---

## Workflow Automation

<p align="center">
  <img src="public/assets/workflow.png" alt="workflow" width="100%">
</p>

---

## Demo Video

Full end-to-end execution demo available here:

▶ https://youtu.be/ONs2RsDuWzU

---

## Technology Stack

- n8n Workflow Automation
- GitHub Actions
- GitHub Webhooks
- Semgrep SAST Scanner
- DVNA Vulnerable Node.js Application
- GitHub Issues API
- Python Data Formatting Nodes

---

## Workflow Logic

### Critical / High Severity Findings
Security findings classified as critical or high severity are automatically transformed into individual remediation issues containing:

- vulnerability title
- affected file/path
- CWE/OWASP mapping
- business risk context
- recommended remediation guidance

This simulates the workflow of high-priority AppSec escalation.

### Medium / Low Severity Findings
Non-critical findings are automatically consolidated into a single remediation backlog issue in order to reduce issue noise while maintaining remediation governance visibility.

This mirrors real-world security debt management practices.

---

## Business Value Demonstrated

This project was designed to simulate how modern security engineering teams reduce manual AppSec triage overhead by integrating CI/CD scanners with workflow automation and engineering remediation channels.

Operational outcomes:

- reduced analyst manual triage time
- standardized remediation ticket creation
- improved vulnerability visibility
- reduced engineering notification fatigue
- improved remediation backlog governance

---

## Possible Future Enhancements

- CVSS risk scoring enrichment
- SLA due date automation
- Jira/ServiceNow integration
- Slack/MS Teams security notifications
- DefectDojo synchronization
- LLM-assisted remediation recommendation

---

## Repository Purpose

This repository was built as a practical demonstration of DevSecOps automation, security workflow orchestration, and AppSec process engineering using n8n as the automation backbone.

---

## Author

Built by Luis S - linkedin.com/in/luis-s-bb7452aa

Security Engineering • IAM • AppSec • DevSecOps Automation


# Damn Vulnerable NodeJS Application (DVNA)

![dvna-logo](docs/resources/dvna.png)

Damn Vulnerable NodeJS Application (DVNA) is a simple NodeJS application to demonstrate [**OWASP Top 10 Vulnerabilities**](https://www.owasp.org/index.php/Top_10-2017_Top_10) and guide on fixing and avoiding these vulnerabilities. The [fixes](https://github.com/appsecco/dvna/tree/fixes) branch will contain fixes for the vulnerabilities. Fixes for vulnerabilities OWASssP Top 10 2017 vulnerabilities at [fixes-2017](https://github.com/appsecco/dvna/tree/fixes-2017) branch.

The application is powered by commonly used libraries such as [express](https://www.npmjs.com/package/express), [passport](https://www.npmjs.com/package/passport), [sequelize](https://www.npmjs.com/package/sequelize), etc.

## Developer Security Guide book

The application comes with a **developer friendly comprehensive guidebook** which can be used to learn, avoid and fix the vulnerabilities. The guide is available at [docs](/docs) and covers the following

1. Instructions for setting up DVNA
2. Instructions on exploiting the vulnerabilities
3. Vulnerable code snippets and instructions on fixing vulnerabilities
4. Recommendations for avoid such vulnerabilities
5. References for learning more

The blog post for this release is at [https://blog.appsecco.com/damn-vulnerable-nodejs-application-dvna-by-appsecco-7d782d36dc1e](https://blog.appsecco.com/damn-vulnerable-nodejs-application-dvna-by-appsecco-7d782d36dc1e)

You can setup a local gitbook server to access the documentation using the following commands. The documentation will then be accessible on [http://localhost:4000](http://localhost:4000).

```bash
cd docs/
docker run --rm -v `pwd`:/gitbook -p 4000:4000 --name gitbook amontaigu/gitbook gitbook serve
```

## Quick start

Try DVNA using a single command with Docker. This setup uses an SQLite database instead of MySQL.

```bash
docker run --name dvna -p 9090:9090 -d appsecco/dvna:sqlite
```

Access the application at [http://127.0.0.1:9090/](http://127.0.0.1:9090/)

## Getting Started

DVNA can be deployed in three ways

1. For Developers, using docker-compose with auto-reload on code updates
2. For Security Testers, using the Official image from Docker Hub
3. For Advanced Users, using a fully manual setup

Detailed instructions on setup and requirements are given in the Guide Gitbook

### 1. Development Setup

Clone this repository

```bash
git clone https://github.com/appsecco/dvna; cd dvna
```

Create a `vars.env` with the desired database configuration

```bash
MYSQL_USER=dvna
MYSQL_DATABASE=dvna
MYSQL_PASSWORD=passw0rd
MYSQL_RANDOM_ROOT_PASSWORD=yes
```

Start the application and database using `docker-compose`

```bash
docker-compose up
```

Access the application at [http://127.0.0.1:9090/](http://127.0.0.1:9090/)

The application will automatically reload on code changes, so feel free to patch and play around with the application.

### Using Official Docker Image

Create a file named `vars.env` with the following configuration

```bash
MYSQL_USER=dvna
MYSQL_DATABASE=dvna
MYSQL_PASSWORD=passw0rd
MYSQL_RANDOM_ROOT_PASSWORD=yes
MYSQL_HOST=mysql-db
MYSQL_PORT=3306
```

Start a MySQL container

```bash
docker run --rm --name dvna-mysql --env-file vars.env -d mysql:5.7
```

Start the application using the official image

```bash
docker run --rm --name dvna-app --env-file vars.env --link dvna-mysql:mysql-db -p 9090:9090 appsecco/dvna
```

Access the application at http://127.0.0.1:9090/ and start testing!

### Manual Setup

Clone the repository

```bash
git clone https://github.com/appsecco/dvna; cd dvna
```

Configure the environment variables with your database information

```bash
export MYSQL_USER=dvna
export MYSQL_DATABASE=dvna
export MYSQL_PASSWORD=passw0rd
export MYSQL_HOST=127.0.0.1
export MYSQL_PORT=3306
```

Install Dependencies

```bash
npm install
```

Start the application

```bash
npm start
```

Access the application at [http://localhost:9090](http://localhost:9090)

## TODO

- [ ] Link commits to fixes in documentation
- [x] Add new vulnerabilities from OWASP Top 10 2017
- [x] Improve application features, documentation

## Contributing

In case of bugs in the application, please create an issue on github. Pull requests are highly welcome!

## Thanks

[Abhisek Datta - abhisek](https://github.com/abhisek) for application architecture and front-end code

## License

MIT
