# Docker-TF-06
# Docker TF06: Nginx + Redis Stack

Orquestração de stack com *Nginx* (build customizado local) + *Redis* cache com *persistência em volume nomeado* redis_data.

*Cenário atendido:*
- Nginx via build: ./nginx
- Redis: redis:alpine + volume
- DNS interno: web pinga "cache"
- Portas: Nginx em localhost:8080

## 📁 Estrutura
[+] Building 3.2s (8/8) FINISHED                                    docker:default
 => [internal] load build definition from Dockerfile               0.0s
 => => transferring dockerfile: 72B                                0.1s
 => [internal] load .dockerignore                                  0.0s
 => => transferring context: 2B                                    0.0s
 => [nginx-web 1/2] FROM docker.io/library/nginx:alpine@sha256:... 0.8s
 => [nginx-web internal] load build context                        0.0s
 => => transferring context: 32B                                   0.0s
 => [nginx-web 2/2] WORKDIR /usr/share/nginx/html                  0.1s
 => exporting to image                                             0.1s
 => => exporting layers                                            0.0s
 => => writing image sha256:...                                    0.0s
 => => nadocker.io/library/nginx:alpine@sha256:.
