- [RabbitMQ](#RabbitMQ)
  - [Plugins](#plugins)
  - [Como executar o Dockerfile](como-executar-o-dockerfile)
  - [Comando sem plugins habilitados](#comando-sem-plugins-habilitados)
  - [Acessar o RabbitMQ](#acessar-o-rabbitmq)
- [Referências](#referências)

# RabbitMQ
Comando docker para instalar a imagem do RabbitMQ 4.0.1 com gerenciador. 

## Plugins 
Alguns plugins são habilitados, eles são:

- rabbitmq_management_agent
- rabbitmq_prometheus
- rabbitmq_shovel
- rabbitmq_shovel_management 

## Como executar o Dockerfile

1. Abram o `CMD` ou `PowerShell`
2. Vá na pasta **docker\RabbitMQ** que tem o  arquivo **Dockerfile**;
3. Execute o comando do docker build para construir a imagem com o nome _rabbitmq_custom_
    
    ```sh    
    docker build -t rabbitmq_custom .
    ```

4. Execute o comando do docker run que irá rodar o container com a imagem criada
    
    ```sh    
    docker run -d --name rabbitmq-4.0.1-management -p 5672:5672 -p 8081:15672 rabbitmq_custom
    ```

## Comando sem plugins habilitados

Abra o `CMD` ou `PowerShell` e execute o seguinte comando:

```sh
docker run -it --rm --name rabbitmq-4.0.1-management -p 5672:5672 -p 8081:15672  -e RABBITMQ_DEFAULT_USER=guest -e RABBITMQ_DEFAULT_PASS=guest rabbitmq:4.0.1-management
```


| Parâmetro | Descrição |
|--|--|
| -rm | Remova automaticamente o contêiner quando ele sair do`CMD` ou `PowerShell`. |
| -it | |
| --name | tribuir um nome ao contêiner. |
| -p | Publicar a(s) porta(s) de um contêiner no host. |

## Acessar o RabbitMQ
Se todos os passos estiverem certos, basta acessar a página do RabbitMQ: http://localhost:8081/ e colocar o usuário e a senha padrão que é: **usuário** = `guest`e **senha** = `guest`

# Referências

- [RabbitMQ - Installing RabbitMQ](https://www.rabbitmq.com/download.html)

- [RabbitMQ - Shovel](https://www.rabbitmq.com/docs/shovel)

- [RabbitMQ - Prometheus](https://www.rabbitmq.com/docs/prometheus)

- [Docker Hub - RabbitMQ](https://hub.docker.com/_/rabbitmq)

- [Rocketseat - (Dockerfile) Principais comandos para criar a receita da imagem](https://blog.rocketseat.com.br/dockerfile-principais-comandos-para-criar-a-receita-da-imagem/)

- [Medium - RabbitMQ com docker conhecendo](https://medium.com/xp-inc/rabbitmq-com-docker-conhecendo-o-admin-cc81f3f6ac3b)

- [Medium - Introdução ao RabbitMQ](https://medium.com/@programadriano/introdu%C3%A7%C3%A3o-ao-rabbitmq-4bfba460ad03)

- [Docker Docs - Containerize an application](https://docs.docker.com/get-started/02_our_app/)

[top](#top)