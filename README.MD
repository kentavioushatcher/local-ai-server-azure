# Local AI Server with Azure Security

## Overview
A self-hosted AI chat server running Llama 3.2 locally,
secured with Azure Entra ID SSO and Azure Key Vault.

## Tech Stack
- Ollama (LLM inference engine)
- Open WebUI (chat interface)
- Docker & Docker Compose (containerization)
- Caddy (reverse proxy + TLS encryption)
- Azure Entra ID (Microsoft SSO authentication)
- Azure Key Vault (secret management)

## Architecture
- Local AI inference with no data leaving your machine
- HTTPS encryption via Caddy reverse proxy
- Microsoft SSO login via Azure Entra ID
- Secrets stored securely in Azure Key Vault

## Setup Instructions
1. Clone this repo
2. Install Docker Desktop and Ollama
3. Create Azure Entra ID app registration
4. Create Azure Key Vault and add secrets
5. Update docker-compose.yml with your Azure values
6. Run docker-compose up -d
7. Visit https://localhost

## Security Notes

### TLS Encryption
HTTPS is implemented via Caddy reverse proxy with automatic 
certificate management. A self-signed certificate is used for 
localhost development. In a production deployment with a public 
domain, Caddy automatically obtains a trusted certificate from 
Let's Encrypt at no cost — no manual configuration required.

### Secret Management
All credentials are stored in Azure Key Vault instead of 
hardcoded in configuration files. GitHub's secret scanning 
detected and blocked an accidental credential exposure during 
development, demonstrating the importance of secret management 
best practices.

## Skills Demonstrated
- Cloud Security (Azure)
- containerization (Docker)
- Identity & Access Management (SSO/OIDC)
- Secret Management (Key Vault)
- Reverse Proxy & TLS (Caddy)
- Local AI Deployment (Ollama)

## Screenshots

### Login Page (Microsoft SSO)
![Login Page](screenshots/login-page.png)

### AI CHAT Interface
![Chat Interface](screenshots/chat-interface.png)

### Azure Key Vault
![Key Vault](screenshots/Azure-keyvault.png)

### Azure App Registration
![App Registration](screenshots/azure-app-registration.png)
