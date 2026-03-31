# Docker-TF-06
# Docker TF06: Nginx + Redis Stack

Orquestração de stack com *Nginx* (build customizado local) + *Redis* cache com *persistência em volume nomeado* redis_data.

*Cenário atendido:*
- Nginx via build: ./nginx
- Redis: redis:alpine + volume
- DNS interno: web pinga "cache"
- Portas: Nginx em localhost:8080

## 📁 Estrutura
