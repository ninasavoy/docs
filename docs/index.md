# Documentação - Plataformas, Microsserviços e APIs

Bem-vindo à documentação do projeto de Plataformas, Microsserviços e APIs feito por Nina Savoy de Sá

## Repositórios

- [Account](https://github.com/ninasavoy/insper.store.account)
- [Account Service](https://github.com/ninasavoy/insper.store.account-service)
- [Auth](https://github.com/ninasavoy/insper.store.auth)
- [Auth Service](https://github.com/ninasavoy/insper.store.auth-service)
- [Gateway](https://github.com/ninasavoy/insper.store.gateway-service)
- [Exchange](https://github.com/ninasavoy/exchange-service)
- [Product](https://github.com/ninasavoy/product)
- [Product Service](https://github.com/ninasavoy/product-service)
- [Order](https://github.com/ninasavoy/order)
- [Order Service](https://github.com/ninasavoy/order-service)
- [Bottlenecks](https://github.com/ninasavoy/bottlenecks)

## Vídeos
- [Individual](https://drive.google.com/file/d/1rsrB5VhUk_JvrWNspz4rLj4K9EcSFFVo/view?usp=sharing)
- [Grupo](https://youtu.be/XCD1pTsewiA)

## Execução

### 1. Dependências

Verifique que você possui o Docker e o KubeCTL baixados:
´´´bash
kubectl version --client
´´´
´´´bash
docker --version
´´´

Caso não, siga as instruções nesses links:
- [Kubernetes](https://kubernetes.io/docs/tasks/tools/)
- [Docker](https://www.docker.com/products/docker-desktop)

### 2. Compile e instale com Maven

Faça isso dentro de todos os arquivos!

Interface:
```bash
./mvnw clean install
```

Implementação (tem service no nome):
```bash
./mvnw clean package
```

### 3. Docker
Crie uma imagem e suba eles para o Docker
```bash
docker build -t seu-usuario-docker/account-service:latest .
docker push seu-usuario-docker/account-service:latest
```

### 4. Kubernetes

Aplique os manifestos Kubernetes
```bash
kubectl apply -f k8s/k8s.yaml
```

Verifique os pods
```bash
kubectl get pods
```

Acesse o serviço
```bash
kubectl get svc account-service
```