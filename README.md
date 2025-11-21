# 🚀 NebulaHost — Deploy React Apps Instantly

NebulaHost is a lightweight Vercel-style deployment platform where users can **deploy any public React GitHub repository** simply by submitting the repo URL.

No zip uploads.  
No manual configuration.  
Just **paste your GitHub URL → get a live deployment link**.

---

## 🌟 Features

- Deploy any **public GitHub React project**
- Automated build + hosting pipeline
- AWS S3-powered static hosting
- Redis caching for deployment status
- Microservices architecture (Upload Service + Deploy Service)
- Real-time status polling from UI
- Clean React dashboard for deployments

---

## 🧠 How NebulaHost Works
GitHub Repo URL → Clone → Build → Upload to AWS → Live Deployment URL

### Steps:
1. User submits a **public GitHub repo URL**
2. NebulaHost **clones the repo**
3. System installs dependencies and builds:
4. Build output is uploaded to AWS S3
5. A **live deployed URL** is returned to the user

---

