# nodejs-demo-app

A sample Node.js (Express) app with a CI/CD pipeline built on GitHub Actions.

## Pipeline

On every push to `main`, `.github/workflows/main.yml` runs:

1. **Test**: installs dependencies and runs the Jest tests.
2. **Build and Push**: builds the Docker image and pushes it to Docker Hub (only if tests pass).

## Required GitHub secrets

| Name | Value |
|---|---|
| `DOCKERHUB_USERNAME` | Your Docker Hub username |
| `DOCKERHUB_TOKEN` | A Docker Hub access token (Read & Write) |

## Run locally

```bash
npm install
npm test
npm start        # http://localhost:3000
```

## Run with Docker

```bash
docker build -t nodejs-demo-app .
docker run -p 3000:3000 nodejs-demo-app
```
