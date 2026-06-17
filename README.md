# Automated DevOps Pipeline Dashboard

A beautiful, interactive dashboard showcasing a complete CI/CD pipeline with Docker, GitHub Actions, and AWS EC2.

## 🚀 Features

- **Interactive Visual Pipeline** - 6-stage flow diagram with animations
- **Responsive Design** - Built with Tailwind CSS
- **Zero Build Steps** - Uses CDN for Tailwind, works out of the box
- **Docker Ready** - Lightweight nginx:alpine container
- **CI/CD Automation** - Complete GitHub Actions workflow
- **AWS EC2 Deployment** - Automated SSH deployment

## 📋 Pipeline Stages

1. **Local Code Changes** - Developer modifications
2. **GitHub Push** - Push to main branch
3. **GitHub Actions Build & Push** - Automated Docker build
4. **Docker Hub Registry** - Image storage
5. **SSH to AWS EC2** - Secure connection to server
6. **Docker Container Run** - Live deployment

## 🔧 Setup Instructions

### 1. Add GitHub Secrets

Go to your repository Settings → Secrets and add:

- `DOCKER_HUB_USERNAME` - Your Docker Hub username
- `DOCKER_HUB_TOKEN` - Docker Hub Personal Access Token
- `EC2_HOST` - EC2 instance public IP or DNS
- `EC2_USERNAME` - SSH user (default: `ec2-user` for Amazon Linux 2023)
- `EC2_PRIVATE_KEY` - Full contents of your `.pem` file

### 2. Local Testing

```bash
docker build -t devops-dashboard .
docker run -p 80:80 devops-dashboard
```

Visit `http://localhost` in your browser.

### 3. Deploy

Push to `main` branch to trigger the workflow:

```bash
git add .
git commit -m "Initial DevOps dashboard setup"
git push origin main
```

Monitor deployment in Actions tab.

## 📁 File Structure

```
.
├── index.html                      # Dashboard UI
├── Dockerfile                      # Container config
├── .github/workflows/deploy.yml    # CI/CD pipeline
└── README.md                       # Documentation
```

## 🎨 Customization

Edit `index.html` to:
- Change colors and gradients
- Modify pipeline stages
- Update descriptions

## ⚙️ Technologies

- **Frontend** - HTML, Tailwind CSS
- **Container** - Docker, nginx
- **CI/CD** - GitHub Actions
- **Cloud** - AWS EC2

## 📝 License

MIT