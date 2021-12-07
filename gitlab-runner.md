## ** Gitlab-Runer **

**1. Создание docker runner**
```
sudo gitlab-runner register -n\
  --url "https://gitlab.com/" \
  --registration-token "...." \
  --description "Docker runner" \
  --executor "docker" \
  --docker-image "docker:latest" \
  --docker-volumes /var/run/docker.sock:/var/run/docker.sock \
  --tag-list docker-runner
```





