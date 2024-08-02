# Desenvolvimento de um App com FastAPI, Vue.js e Docker
### Como foi desenvolvido
### 
Exercicio realizado conforme o seguinte [post](https://course.upiara.com/fasttrack/fastapi_and_vuejs/2docker_and_postgres/2docker_and_postgres/).


## Como executar o projeto

Construindo e executando os containers:

```sh
$ docker-compose up -d --build
```

Aplicando as migrações:

```sh
$ docker-compose exec backend aerich upgrade
```

Verifique [http://localhost:5000](http://localhost:5000), [http://localhost:5000/docs](http://localhost:5000/docs), e [http://localhost:8080](http://localhost:8080) estão funcionando normalmente.
