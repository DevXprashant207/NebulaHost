📦 NebulaHost — React App Hosting Platform
NebulaHost is a lightweight, Vercel-inspired hosting platform that allows users to deploy React applications seamlessly.
It provides a smooth workflow where users can upload their project, trigger a deployment pipeline, and host their app instantly.

Built with a modern stack — React, Express.js, AWS SDK, Redis, and Simple-Git, NebulaHost demonstrates a scalable microservices architecture tailored for frontend deployments.

🚀 Features
One-click React app deployment

Microservices-based architecture

Deployment service powered by AWS SDK + Redis

Upload service using Express.js + Simple-Git

React-based dashboard for app management

Real-time deployment logs

Redis caching for fast deployment status retrieval

Scalable architecture inspired by Vercel’s deployment flow

🏗️ Tech Stack
Frontend
React.js

TailwindCSS

Axios

Vite (optional)

Backend
Node.js

Express.js

AWS SDK

Simple-Git

Redis

Infrastructure
AWS S3

AWS EC2 / local server

Redis Server

Nginx (optional, for reverse proxy)

📂 Project Structure
nebula-host/
│
├── deploy-service/        # Handles AWS deployments & build process
├── upload-service/        # Handles project file uploads
├── frontend/              # React dashboard UI
│
├── shared/                # Constants, utilities, configs
└── README.md
⚙️ How It Works
User uploads a React project

Upload service saves it locally

Simple-Git handles versioning

Deployment is triggered

Deploy-service fetches project

Builds the React app

Uploads build artifacts to AWS S3 (or any hosting bucket)

Redis stores deployment status

Allows real-time updates

Faster retrieval for dashboards

User gets a public hosting URL

Similar to Vercel’s output links

🛠️ Installation & Setup
1️⃣ Clone the Repository
git clone https://github.com/DevXprashant207/NebulaHost.git
cd NebulaHost
2️⃣ Install dependencies
Upload Service:
cd upload-service
npm install
Deploy Service:
cd deploy-service
npm install
Frontend:
cd frontend
npm install
3️⃣ Setup Environment Variables
Deploy Service (deploy-service/.env)
AWS_ACCESS_KEY=your_key
AWS_SECRET_KEY=your_secret
AWS_REGION=your_region
S3_BUCKET_NAME=your_bucket
REDIS_URL=redis://localhost:6379
Upload Service (upload-service/.env)
UPLOAD_DIRECTORY=/uploads
REDIS_URL=redis://localhost:6379
Frontend (frontend/.env)
VITE_API_URL=http://localhost:5000
4️⃣ Run Services
Upload Service
cd upload-service
npm run start
Deploy Service
cd deploy-service
npm run start
Frontend Dashboard
cd frontend
npm run dev
🌐 Deployment Flow
User Upload → Upload-Service → Deploy-Service → Build → AWS S3 → Public URL
📡 API Endpoints
POST /upload
Upload a React project .zip file.

POST /deploy
Trigger deployment for a project.

GET /status/:id
Get deployment status from Redis.

📈 Future Improvements
Custom domain support

CI/CD pipeline integration

Realtime WebSocket logs

User authentication and teams

Build analytics & usage insights

Multi-framework support (Next.js, Vue)

🧑‍💻 Author
Prashant
Building developer tools & full-stack products.
GitHub: https://github.com/DevXprashant207
