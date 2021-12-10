## ** Gitlab-Runer **

**1. Создание docker runner с пробросом сокета docker**
```
sudo gitlab-runner register -n\
  --url "https://gitlab.com/" \
  --registration-token ... \
  --description "Docker runner" \
  --executor "docker" \
  --docker-image "docker:latest" \
  --docker-volumes /var/run/docker.sock:/var/run/docker.sock \
  --tag-list docker-runner
```

**2. Создание docker runner с привилегиями**
```
sudo gitlab-runner register -n\
  --url https://gitlab.com/ \
  --registration-token ... \
  --description "Docker runner priv" \
  --executor docker \
  --docker-image "docker:latest" \
  --docker-privileged \
  --tag-list docker-runner-priv
```

**3. Создание shell runner с привилегиями**
```
sudo gitlab-runner register -n\
  --url https://gitlab.com/ \
  --registration-token ... \
  --description "Shell runner" \
  --executor shell \
  --tag-list shell-runner
```