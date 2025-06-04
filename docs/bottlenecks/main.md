# Bottlenecks
## Cacheability

Foi adicionada cacheabilidade ao microsserviço product para otimizar o desempenho das requisições. A implementação utiliza a anotação @Cacheable do Spring, que permite armazenar em memória o resultado de métodos frequentemente acessados, como buscas por produtos.

Com isso, ao invés de consultar o banco de dados a cada requisição, os dados já processados são retornados diretamente do cache, reduzindo o tempo de resposta e a carga no banco. Essa estratégia é especialmente útil para endpoints que retornam dados que não mudam com frequência.

A configuração do cache foi feita com foco em performance e controle de validade dos dados, podendo ser estendida com soluções como Redis, caso necessário no futuro.