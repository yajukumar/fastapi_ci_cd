1. Create a git hub repository
2. add git hub action yml file
3. add secrets
  Steps to Add Docker Hub Credentials in GitHub

  Go to your GitHub repository → Settings → Secrets and variables → Actions → New repository secret.

  Add two secrets:

  Name	Value
  DOCKER_USERNAME	your Docker Hub username
  DOCKER_PASSWORD	your Docker Hub password or Personal Access Token


4 -- Pull docker image from hub and run on local
  docker pull yajukumar/fastapi-app:latest
  docker run -d --name fastapi_app -p 8000:8000 yajukumar/fastapi-app:latest
