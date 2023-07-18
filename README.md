## gitea-actions-practice

### How to use
```sh
docker compose up -d gitea
```
Run gitea and configure default env

Go to http://localhost:3000/admin/actions/runners and get registration token (ex. `bMTsKZqzq3JPpIea8lYQJSmDFhbiz4MikoNyTXf3`)

```sh
RUNNER_TOKEN={your_token} docker compose up -d gitea_act_runner -e
```
Run gitea act runner with your token

```sh
ngrok http --domain={your_ngrok_domain} {act runner port?}
```
Use ngrok to expose gitea runner

///
(?) Configure GitHub repo webhook URL to ngrok URL

### Troubleshooting

#### Cannot ping the Gitea instance server

> 2023-07-19 00:11:07 level=error msg="Cannot ping the Gitea instance server" error="unavailable: dial tcp 127.0.0.1:3000: connect: connection refused"

https://gitea.com/gitea/act_runner/src/commit/73adae040d2eba41ce80ce64d1eba23f07a95d1e/internal/pkg/config/config.example.yaml#L24

Set `runner.insecure: true`

And check docker network

### Reference
- https://docs.gitea.com/next/installation/install-with-docker
- https://gitea.com/gitea/act_runner
