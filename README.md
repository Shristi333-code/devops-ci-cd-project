# End-to-End CI/CD Pipeline for a Java Web Application

Student Feedback Portal: a Java Maven web app (WAR) built, tested and deployed automatically using **Git + Maven + Jenkins + Apache Tomcat**.

## Tools Used
- Git and GitHub (main, dev, feature branches, version tags)
- Maven (build, test, package as WAR)
- Jenkins (declarative pipeline using the Jenkinsfile)
- Apache Tomcat 10.1.34 (runs on port 8081)
- Linux (Kali on WSL2), OpenJDK 21

## Pipeline Stages
1. Checkout
2. Build
3. Test
4. Package
5. Archive
6. Deploy (copy WAR to Tomcat webapps)
7. Verify (health check)

If the health check fails, the previous WAR is restored (rollback).

## Application URLs
- App: http://localhost:8081/app/
- Health check: http://localhost:8081/app/health

## Git Branching
- `main`: stable code, release tags (v1.0)
- `dev`: integration branch
- `feature/*`: short-lived feature branches

## Failure and Rollback Demos
- **Case A:** A failing unit test stops the pipeline before deploy.
- **Case B:** A bad WAR gives HTTP 404, and the backup WAR is restored (HTTP 200).
- **Case C:** `git revert` on a bad commit, then Jenkins redeploys good code.

## Documentation
Full report with screenshots: `DevOps_CICD_Project_Solution_v5.docx`

## Demo Video
<VIDEO LINK>

## Dataset
Dataset not required; the primary project input is source-code changes.

## Author
Shristi
