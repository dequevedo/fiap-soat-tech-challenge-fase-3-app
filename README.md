# O Problema

A lanchonete está enfrentando um alto número de requisições devido ao aumento da demanda. 
Para lidar com essa carga e garantir alta disponibilidade e escalabilidade, 
foi implementado um cluster Kubernetes (K8s) preparado para fazer o autoscaling dos PODs com HPA.

---

# Diagrama da Arquitetura Kubernetes

![K8S_Architecture](assets/KubernetesArchitecture.png)

---

# Como executar este projeto

### Requisitos
1. WSL no Windows
2. Docker
3. Docker Desktop
4. Kubernetes
5. Helm
6. Ngrok
6. (Opcional) Lens


### 2. Construir a Imagem Docker

```sh
docker build -t tech-challenge-fase-1 .
```

### 3. Aplicar todos os Manifests do Aplicativo no Kubernetes

```sh
helm install fiap-tech-challenge ./infra
```

ou, caso deseje atualizar o aplicativo:

```sh
helm upgrade --install fiap-tech-challenge ./infra
```

### 4. Testar o aplicativo

```sh
curl -X GET "localhost:30080/customers"
```

---

### Executando contêineres Docker

1. Acesse a pasta onde o arquivo `docker-compose.yml` está localizado.
2. Execute o comando:

```sh
docker compose up -d
```

---

### Acessando a documentação OpenAPI/Swagger

1. Abra o URL no seu navegador:

```sh
http://localhost:30080/swagger-ui/index.html
```
