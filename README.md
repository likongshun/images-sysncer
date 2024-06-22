# images-sysncer
Github Action 镜像拉取同步

https://cr.console.aliyun.com/cn-hangzhou/instances

**gitea/act_runner:nightly**
skopeo copy docker://docker.io/gitea/act_runner:nightly docker://registry.cn-hangzhou.aliyuncs.com/likongshun/act_runner:nightly

**ghcr.io/home-assistant/home-assistant:stable**
skopeo copy docker://ghcr.io/home-assistant/home-assistant:stable docker://registry.cn-hangzhou.aliyuncs.com/likongshun/home-assistant:stable

**ghcr.io/music-assistant/server:latest**
skopeo copy docker://ghcr.io/music-assistant/server:latest docker://registry.cn-hangzhou.aliyuncs.com/likongshun/server:latest

**docker.io/gitea/runner-images:ubuntu-latest**
skopeo copy docker://docker.io/gitea/runner-images:ubuntu-latest docker://registry.cn-hangzhou.aliyuncs.com/likongshun/runner-images:ubuntu-latest


**./github/workflows/Sync.yml**

```bash
name: Sync Image to Aliyun  Example

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Git pull
      uses: actions/checkout@v3

    - name: Set up Docker Buildx
      uses: docker/setup-buildx-action@v2.9.1

    - name: Login to Docker Hub
      uses: docker/login-action@v2.2.0
      with:
        registry: registry.cn-hangzhou.aliyuncs.com
        username: likongshun@aliyun.com
        password: Test@10010
        logout: false

    - name: Use Skopeo Tools Sync Image to Docker Hub
      run: |
         skopeo copy docker://docker.io/gitea/runner-images:ubuntu-latest docker://registry.cn-hangzhou.aliyuncs.com/likongshun/runner-images:ubuntu-latest
```


