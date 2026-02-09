# Capstone Project

Docker Containerization and Multi-Stage CI/CD Pipeline
- Node.js microservices application with Nginx proxy and Redis database
- Automated deployment to Azure App Service via GitHub Actions

## Local Development

```bash
docker-compose up --build
# Access at http://localhost
```

## Azure Deployment (GitHub Actions)

### Setup

1. **Create Azure Service Principal:**
```bash
az ad sp create-for-rbac --name "github-actions-sp" --role contributor \
  --scopes /subscriptions/{subscription-id}/resourceGroups/capstone-rg \
  --sdk-auth
```

2. **Add GitHub Secret:**
   - Go to Repository → Settings → Secrets and variables → Actions
   - Create secret: `AZURE_CREDENTIALS`
   - Paste the JSON from step 1

3. **Push to main/master** - Deployment runs automatically!

**ACR:** capstone1.azurecr.io  
**Web App:** https://capstone-webapp.azurewebsites.net


