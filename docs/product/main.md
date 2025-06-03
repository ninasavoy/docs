# Product

O Product e o Product Services são microsserviços da loja, desenvolvidos em Java. Utilizamos o Jenkins, garantindo que os serviços sejam testados e implantados de forma contínua. Também configuramos o Minikube para simular um cluster Kubernetes local, permitindo testar os deployments dos microsserviços em um ambiente semelhante ao de produção.

A API possui o seguinte endpoint:

!!! info "GET /product/"

    Obtenha as informações de todos os produtos cadastrados. Ex: `GET /product`.

    === "Response"

        ``` { .json .copy .select linenums='1' }
        [
            {
                "id": "d5f06af4-8319-4d81-bd4e-42eda1fdeb22",
                "name": "goiabada",
                "price": 15.5,
                "unit": "pao de açucar"
            },
            {
                "id": "64b69c92-aed0-410d-843a-b2499ed1f293",
                "name": "vinho",
                "price": 60.5,
                "unit": "st marche"
            },
            {
                "id": "5d61fed5-be41-452c-87a8-33b55715fd77",
                "name": "queijo",
                "price": 30.2,
                "unit": "st marche"
            }
        ]
        ```
        ```bash
        Response code: 200 (ok)
        ```
        
Também existe rotas de deleção, inserção e busca específicas!

A API está disponível nos seguintes repositórios: [Product](https://github.com/ninasavoy/product){target="_blank"} | [ProductService](https://github.com/ninasavoy/product-service){target="_blank"}.

## Estrutura do Projeto

```
src/main/
    java/store/product/
    ├── Product.java
    ├── etc.java
    resouces/
        db/
        application.yaml
Dockerfile
Jenkinsfile
pom.xml
```

```
k8s
src/main/java/store/product
├── ProductController.java
├── ProductIn.java
├── ProductOut.java
Jenkinsfile
pom.xml
```

## Código-fonte

=== "ProductX.java"
    ``` { .python .copy .select linenums="1" }
    --8<-- "https://raw.githubusercontent.com/ninasavoy/product/src/main/java/store/product/ProductX.java"
    ```

=== "Dockerfile"
    ``` { .dockerfile .copy .select linenums="1" }
    --8<-- "https://raw.githubusercontent.com/ninasavoy/product-service/Dockerfile"
    ```