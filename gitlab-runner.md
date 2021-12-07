## ** Gitlab-Runer **

**1. Создание docker runner**
```
sudo gitlab-runner register \
  --url "https://gitlab.com/" \
  --registration-token "PROJECT_REGISTRATION_TOKEN" \
  --description "Docker runner" \
  --executor "docker" \
  --docker-image "docker:latest" \
  --docker-volumes /var/run/docker.sock:/var/run/docker.sock \
  --tag-list docker-runner
```





