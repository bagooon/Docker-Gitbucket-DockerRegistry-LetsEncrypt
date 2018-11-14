# Docker-Gitbucket-DockerRegistry-LetsEncrypt
gitbucket and Docker-registry and Let's Encrtypt Runs on Docker

# How to run

1. Install Docker Compose and Git on your development host. The rest of the requirements will be installed in a container.
1. Download the Docker-Gitbucket-DockerRegistry-LetsEncrypt source code:
1. Create an account for Docker-registry (Basic Authentication)
```
mkdir -p registry gitbucket registry/auth 
docker run --entrypoint htpasswd registry:2 -Bbn ENTER-YOUR-ACCOUNT ENTER-YOUR-PASSWORD > registry/auth/htpasswd
```
1. open '.env' and replace host and email
```
# Your Email Address
LETSENCRYPT_EMAIL=ENTER-YOUR-EMAIL-HERE

# Your Gitbucket Host
GITBUCKET_DOMAIN=ENTER-YOUR-GITBUCKET-HOST-HERE

# Your Docker Registry Host
DOCKER_REGISTRY_DOMAIN=ENTER-YOUR-REGISTRY-HOST-HERE
```
1. Start containers
```docker-compose up -d```