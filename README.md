#  Automated CI/CD Pipeline Proof of Concept

##  Project Overview
This project demonstrates a fully automated **CI/CD (Continuous Integration / Continuous Deployment)** pipeline. The goal was to eliminate manual file transfers by creating a system where code changes are automatically detected and deployed.

##  Tools Used
* **Docker**: Hosts the Jenkins environment in an isolated container.
* **Jenkins**: Orchestrates the automation and handles the deployment logic.
* **GitHub**: Functions as the Source Control Management (SCM) system.
* **Jenkinsfile (Groovy)**: Defines the "Pipeline as Code."

##  The Flow
1. **Commit**: A developer makes changes to `index.html` on GitHub.
2. **Poll SCM**: Jenkins checks GitHub every minute for updates.
3. **Build**: Jenkins pulls the latest code and executes the `Jenkinsfile`.
4. **Deploy**: The file is moved to the production folder on the server using `rsync`.

