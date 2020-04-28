# Kafka Camunda PoC

This module uses automatic BPMN deployment

## Tecnologias utilizadas

- Java > 1.8
- Maven
- PostgreSQL
- Docker/Docker-Compose
- Spring Boot
- Kafka
- Camunda
- Camunda Modeler

## Instalação

- Docker (No caso de sistemas linux, ex.: Linux Ubuntu 18.04, para detalhes segue o link - compose install - na 
descrição): 

    ```
    $ sudo apt update && sudo apt upgrade
    
    $ sudo apt-get install apt-transport-https ca-certificates curl gnupg software-properties-common
    
    $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    
    $ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
    
    $ sudo apt install docker-ce
    
    $ sudo systemctl enable docker
    
    $ sudo systemctl start docker
    
    $ sudo systemctl status docker
    
    $ docker -v
    ```
- Docker Compose: https://docs.docker.com/compose/install/

    ```
    $ sudo apt-get install docker-compose
    ```
- Maven: https://maven.apache.org/install.html

- Camunda Modeler: https://camunda.com/download/modeler/

## 1. Baixar codigo fonte

Codigo fonte: https://github.com/ErikMarquesZup/camunda-kafka/tree/poc/kafka-request-reply

## 2. Acessar o repositorio local

```
$ cd camunda-kafka
```

### 3. Iniciar o docker compose

```
$ docker-compose -f docker-compose-local.yml up
```

### 4. Build no projeto

```
$ mvn clean install
```

### 5. Para terminar o processamento dos containers via docker-compose

CRTL + C

```
$ docker-compose -f docker-compose-local.yml down --remove-orphans
```

### Comandos uteis do DOCKER

### 1. Parar todos os containers

```
$ docker stop $(docker ps -aq)
```

### 2. Remover todos os containers

```
$ docker rm $(docker ps -aq)
```

### 3. Remover todos os volumes

```
$ docker volume rm $(docker volume ls -qf dangling=true)
```
