# Github Action  images-sysncer

https://cr.console.aliyun.com/cn-hangzhou/instances

## Home assistant

- **ghcr.io/home-assistant/home-assistant:stable**
skopeo copy docker://ghcr.io/home-assistant/home-assistant:stable docker://registry.cn-hangzhou.aliyuncs.com/likongshun/home-assistant:stable

- **ghcr.io/music-assistant/server:latest**
skopeo copy docker://ghcr.io/music-assistant/server:latest docker://registry.cn-hangzhou.aliyuncs.com/likongshun/server:latest

- **nodered/node-red**
skopeo copy docker://ghcr.io/nodered/node-red:latest docker://registry.cn-hangzhou.aliyuncs.com/likongshun/node-red:latest

- **emqx/emqx**
skopeo copy docker://ghcr.io/emqx/emqx:latest docker://registry.cn-hangzhou.aliyuncs.com/likongshun/emqx:latest



## Gitea

- **gitea/act_runner:nightly**
  skopeo copy docker://docker.io/gitea/act_runner:nightly docker://registry.cn-hangzhou.aliyuncs.com/likongshun/act_runner:nightly

- **docker.io/gitea/runner-images:ubuntu-latest**
  skopeo copy docker://docker.io/gitea/runner-images:ubuntu-latest docker://registry.cn-hangzhou.aliyuncs.com/likongshun/runner-images:ubuntu-latest

- **docker.io/gitea/gitea:latest**
  skopeo copy docker://docker.io/gitea/gitea:latest docker://registry.cn-hangzhou.aliyuncs.com/likongshun/gitea:latest

```bash
vi ./github/workflows/Sync.yml
```

