# Serverless Website with Azure DevOps CI/CD

This project demonstrates a complete CI/CD pipeline for a serverless website using Azure DevOps and Azure Static Web Apps.

## Architecture

- **Frontend**: React with TypeScript and Tailwind CSS
- **Hosting**: Azure Static Web Apps
- **CI/CD**: Azure DevOps Pipelines
- **Source Control**: Azure DevOps Repos

## CI/CD Pipeline

The CI/CD pipeline is configured to automatically build, test, and deploy the application to different environments based on the branch:

- **develop branch**: Deploys to Development environment
- **main branch**: Deploys to Test environment, and then to Production after approval

### Pipeline Stages

1. **Build Stage**:
   - Install dependencies
   - Run linting
   - Build the application
   - Archive and publish build artifacts

2. **Deploy to Development**:
   - Triggered by changes to the develop branch
   - Deploys to the Development environment

3. **Deploy to Test**:
   - Triggered by changes to the main branch
   - Deploys to the Test environment

4. **Deploy to Production**:
   - Requires successful deployment to Test
   - Deploys to the Production environment

## Environment Configuration

The application uses environment-specific configuration files:

- `.env.development` - Development environment variables
- `.env.test` - Test environment variables
- `.env.production` - Production environment variables

## Setup Instructions

### Prerequisites

- Azure DevOps account
- Azure subscription
- Node.js and npm installed

### Azure DevOps Setup

1. Create a new project in Azure DevOps
2. Import or push this repository to Azure Repos
3. Create three Azure Static Web Apps (Development, Test, Production)
4. Get the deployment tokens for each Static Web App
5. Add the tokens as pipeline variables:
   - `AZURE_STATIC_WEB_APP_DEV_TOKEN`
   - `AZURE_STATIC_WEB_APP_TEST_TOKEN`
   - `AZURE_STATIC_WEB_APP_PROD_TOKEN`
6. Create a new pipeline using the existing `azure-pipelines.yml` file

### Local Development

1. Clone the repository
2. Install dependencies:
   ```
   npm install
   ```
3. Start the development server:
   ```
   npm run dev
   ```

## Branching Strategy

- `main`: Production-ready code
- `develop`: Development code
- `feature/*`: Feature branches

## Deployment

The deployment process is fully automated through the Azure DevOps pipeline:

1. Push changes to the appropriate branch
2. Azure DevOps pipeline automatically builds and deploys to the corresponding environment
3. For production deployments, manual approval is required after successful deployment to the Test environment#   s e r v e r l e s s - c i . c d  
 #   s e r v e r l e s s - c i . c d  
 