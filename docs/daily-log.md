## Project Brief
**What this is:** This is my capstone project for the TechCrush Cloud & DevOps Bootcamp. The brief asks me to design, build, document and demo real cloud infrastructure, and to be able to explain every design decision.

**My group:** Group 5. We have to complete two projects:
1. **Dockerized 3-tier app with CI/CD (compulsory for everyone).** A small app called FormFlow with a frontend, a backend and a database, each in its own Docker container. CI/CD stands for Continuous Integration / Continuous Deployment, which means every code push is automatically built, tested and released. Images are tagged with real version labels (never just `latest`) so we always know which version is live and can roll back to the last working one. It deploys to a Linux VM (Virtual Machine, a computer rented in the cloud) through GitHub Actions, GitHub's built-in automation tool.
2. **Zero-downtime blue-green deployment (Groups 5 and 6).** A checkout service called QuickTill must update with no downtime. Blue is the live version and green is the new version waiting beside it. It uses Azure App Service slots, a health check that must pass before traffic switches, and a tested rollback.

**What I have to deliver for both projects:**
- A GitHub repo with a clear folder structure and working code
- A Phase 0 design worksheet (design decisions written before building)
- Documentation with screenshots, a demonstrated rollback, and an incident report
- A live demo, with the deployment reachable on a public address using port 80 only

**Tools:** Docker, Docker Compose, Docker Hub, GitHub Actions, a Linux VM, Azure App Service, VS Code and PowerShell.

**Timeline:** Exams end on 3 Dec. The project is due about a week after, around 10 Dec. During exams I am doing small daily tasks (design worksheets and setup), and the heavy building starts after exams.

**How I am documenting:** I am keeping a daily log with a screenshot evidence section, and I will write a short README at the end.

---

## Day 1: Repo setup
**Date:** 24 Nov 2026
**Project:** Both

**Today's task:**
Today is day 1 of me working on my TechCrush capstone project. I have about two and a half weeks to complete it. I have decided to use an AI to break the project down into a day-by-day plan, and I'll be starting the first week and a half light because I'm a university student in the middle of exams. When they end, that is when the heavy lifting starts.

For today's task, I made my working directories: a folder for my daily logs, evidence, app, and workflow.

**What I did:**
- Made the folders (app, docs, screenshots and .github/workflows)
- Created the daily-log.md file and the placeholder files
- Initialised the Git repo and pushed it to GitHub

**What gave me issues:**
- I created the GitHub repo with the "Add README" option on before pushing, so GitHub already had a commit my laptop didn't. A normal push would have been rejected because the two histories didn't match.
- I fixed it by connecting the repo with `git remote add origin`, then running `git pull origin main --allow-unrelated-histories` to merge GitHub's README with my local files, and then `git push -u origin main`.
- A text editor opened asking for a merge message and the terminal looked stuck ("Waiting for your editor to close the file"). I saved and closed the `MERGE_MSG` tab and the merge finished.
I used `mkdir` to make the folders, `cd` to move through them, and a command I learnt today, `New-Item`, which is used to make a new item/file.

**What I found out:**
- `New-Item` is a way to create files, which makes it easier to create several files in one command.
- `code .` reopens VS Code inside the folder you are working in/just made.

**What gave me issues:**
- Nothing gave me any issues today (so far).

**Evidence:**
- `screenshots/day01-folder-structure.png`: the project folders and files created in VS Code
- `screenshots/day01-github-repo.png`: the repo on GitHub showing the same folders

**Next up (Day 2, Wed 25 Nov, about 20 minutes):**
Set up Docker.
1. Create a free account at hub.docker.com. Docker Hub is the online store where my app's images will be kept.
2. Create an access token (Account Settings, then Personal access tokens, then Generate new token). It is a password-like key for tools and pipelines, and I will keep it private and never put it in the repo.
3. In the VS Code terminal, run `docker --version` to check that Docker is installed, then `docker run hello-world` to confirm it works.
4. Take a screenshot of the "Hello from Docker!" message as `screenshots/day02-docker-works.png`.