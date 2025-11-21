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

# 📩 API Endpoints

## 🔹 1. Deploy React App (Using GitHub URL)

### **POST /deploy**

**Request Body:**

```json
{
"repoUrl": "https://github.com/username/repo-name"
}

Example cURL:

curl -X POST https://api.nebulahost.com/deploy \
  -H "Content-Type: application/json" \
  -d '{"repoUrl": "https://github.com/username/my-react-app"}'
Response:

{
  "deploymentId": "ab12cd34",
  "status": "queued"
}
🔹 2. Check Deployment Status
GET /status/:deploymentId
curl https://api.nebulahost.com/status/ab12cd34
Response:

{
  "status": "success",
  "url": "https://project123.nebulahost.com"
}
🏗️ Tech Stack
Frontend
React.js

TailwindCSS

Axios

Backend
Node.js

Express.js

Simple-Git

AWS SDK

Infrastructure
AWS S3

Redis

Nginx (optional)

Architecture
Microservices

REST APIs

Deployment pipeline

🧰 Project Structure
nebula-host/
│
├── deploy-service/     # Clones repo → Builds → Uploads to AWS
├── upload-service/     # Receives GitHub URL → Triggers deploy
├── frontend/           # Dashboard UI
└── shared/             # Config, utils, constants
⚙️ Running Locally (Developer Setup)
1️⃣ Clone the repo
git clone https://github.com/DevXprashant207/NebulaHost.git
cd NebulaHost
2️⃣ Install dependencies
Deploy Service
cd deploy-service
npm install
Upload Service
cd upload-service
npm install
Frontend
cd frontend
npm install
3️⃣ Configure environment variables
Deploy Service → deploy-service/.env
AWS_ACCESS_KEY=xxx
AWS_SECRET_KEY=xxx
AWS_REGION=ap-south-1
S3_BUCKET_NAME=nebula-host-bucket
REDIS_URL=redis://localhost:6379
Upload Service → upload-service/.env
DEPLOY_SERVICE_URL=http://localhost:4000/deploy
Frontend → frontend/.env
VITE_API_URL=http://localhost:5000
4️⃣ Start all services
Upload Service
cd upload-service
npm run start
Deploy Service
cd deploy-service
npm run start
Frontend UI
cd frontend
npm run dev
🌐 Deployment Flow (Detailed)
[Frontend UI] → [Upload API] → [Deploy Service]
             → Clone Repo from GitHub
             → Install Dependencies
             → Build React App
             → Upload 'dist' or 'build' folder to S3
             → Return Public URL
📈 Future Roadmap
Support for Next.js / Vue / Svelte

File-based routing

Custom domains

Authentication & user accounts

Build logs with WebSocket streaming

Teams and collaboration

Analytics dashboard

👨‍💻 Author
Prashant
Full-Stack Developer | Cloud | DevTools
GitHub: https://github.com/DevXprashant207

