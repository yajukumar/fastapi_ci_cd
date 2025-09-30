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

5--
remove old image and run new one
# Stop & remove old containers if they exist
docker rm -f fastapi_app redis_cache 2>/dev/null || true

# Run Redis
docker run -d --name redis_cache -p 6379:6379 redis:7

# Run FastAPI container linked to Redis
docker run -d --name fastapi_app --link redis_cache:redis -p 8000:8000 yajukumar/fastapi-app:latest

