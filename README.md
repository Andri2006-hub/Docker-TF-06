# TF06 - Orquestração com Docker Compose

## 📋 Descrição do Projeto

Este projeto demonstra a orquestração de um stack contendo:
- **Nginx**: Servidor web com build customizado
- **Redis**: Cache com persistência em volume

## 📁 Estrutura de Arquivos

```
lab_compose_tf06/
├── docker-compose.yml    # Configuração de orquestração
├── nginx/
│   ├── Dockerfile        # Build customizado do Nginx
│   └── nginx.conf        # Configuração do servidor
├── index.html            # Página padrão do Nginx
└── README.md             # Este arquivo
```

## 🚀 Como Executar

### Pré-requisitos
- Docker instalado
- Docker Compose instalado

### Passos

1. **Navegar para o diretório do projeto:**
```bash
cd lab_compose_tf06
```

2. **Iniciar o stack:**
```bash
docker-compose up -d
```

3. **Verificar os serviços:**
```bash
docker-compose ps
```

4. **Testar conectividade entre contêineres:**
```bash
docker-compose exec web ping -c 4 cache
```

## 📊 Saída dos Comandos

### docker-compose up -d
Cria e inicia os contêineres em background.

### docker-compose ps
Mostra o status dos serviços:
- **web (tf06-nginx)**: Porto 80:80
- **cache (tf06-redis)**: Porto 6379:6379

### Teste de Conectividade
O serviço web consegue pingar o serviço cache usando o nome interno da rede Docker (DNS):
- Hostname: `cache` ou `tf06-redis`
- Porta: 6379

## 🔗 Rede Interna

Os serviços comunicam-se através da rede `tf06-network`:
- A resolução de nomes é automática via DNS do Docker
- Web acessa Redis como: `cache:6379`

## 💾 Persistência

O volume `redis_data` persiste os dados do Redis:
```bash
docker volume ls | grep redis_data
```

## 🛑 Parar o Stack

```bash
docker-compose down
```

Para remover também os volumes:
```bash
docker-compose down -v
```

## ✅ Verificação

1. Nginx rodando em `http://localhost`
2. Redis acessível internamente em `cache:6379`
3. Volume de persistência criado e funcionando

---

**Aluno:** Seu Nome  
**Data:** 30/03/2026
