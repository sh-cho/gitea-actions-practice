## gitea-actions-practice

### How to use
```sh
docker compose up -d
```
Run gitea and configure default env

http://localhost:3000/admin/
Go to http://localhost:3000/admin/ and create a new user

```sh
docker run -e GITEA_INSTANCE_URL=https://localhost:3000 -e GITEA_RUNNER_REGISTRATION_TOKEN=<your_token> -v /var/run/docker.sock:/var/run/docker.sock --name gitea_runner1 gitea/act_runner:nightly
```
Run gitea act runner

```sh
ngrok http --domain={your_ngrok_domain} {act runner port?}
```
Use ngrok to expose gitea runner

///
(?) Configure GitHub repo webhook URL to ngrok URL

### Reference
- https://docs.gitea.com/next/installation/install-with-docker
- https://gitea.com/gitea/act_runner
