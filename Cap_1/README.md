# O que é `container` ?

Container é nada mais que um isolamento de recursos, que roda dentro de uma instância, porém containers compartilham recursos do, OS ao qual está sendo executado, diferente das maquinas virtuais, o contianer não precisa de recursos como kernel e driver, pense em um container como lojas de um shopping, cada loja tem a sua próprias características e tamanho, mas todas compartilham os recursos do shopping em si, todas estão dentro da estrutura do shopping.

A utilização dos containers se da atravez da utilização de imagens, que podem ou não estar já pré configuradas.

Sabendo desta informação vamos entender qual o papel do `Docker`

# O que é `Docker` ?

`Docker` é uma tecnologia que facilita manusear containers, com o docker você consegue realizar várias funcionalidades com containers de forma muito simples, para mais informações segue [link](https://docs.docker.com/)

![containers_docker](./imgs/containers_docker.png)

---

# O porque trabalhar com containers ?

Containers permitem que uma imagem seja criada e/ou customizada e utilizada de forma simples e rápida por não somente sysadmins, mas também por desenvolvedores de forma simples e pratica. Outros pontos que a utilização de contianers podem te ajuda é na portabilidade de ambiente, você consegue replicar um ambiente rapidamente e sem complicações.

---

# Primeiros passo com `Docker`

## Instalando o docker
Existem alguns meios para realiza a instalanção do `docker`, se você é usuário linux, sua via é bem mais simples você poderá realizar a instalação via `curl`, gerenciado de pacote ou source, já se você é usuário windows até funciona mas eu **NÂO INDICO** por enguanto, existem site que você poderá trabalhar com docker sem muitos problemas, segue link:

- [Linux](https://docs.docker.com/install/linux/docker-ce/centos/)

Bom como falei acima para quem utiliza windows a melhor opção é criar um conta no docker hub e acessar o play with docker, que é uma plataforma gratuita já com docker instalado que lhe permite fazer teste com docker.

- [Play with docker](https://labs.play-with-docker.com/)


---

## Comandos básicos

Após realizar a instalação do docker, vamos checar as informações do mesmo, çomo estamos em 2018 é indicado que você utilize a versão do docker 18.+.


---
**Docker cli - Lógica de utilização**

Para utilizar o docker, primeiramento você deve conher sua logica de comandos, que é bem simple, ele utiliza o formato de subprocess, sequidos por parametros e cada comando possui seus respectivos parametros, vamos aos exemplos:

```
docker <comandos> <parametros>
```

Lista de todos subprocess (comandos).

```
docker container   Manage containers
docker image       Manage images
docker network     Manage networks
docker node        Manage Swarm nodes
docker plugin      Manage plugins
docker secret      Manage Docker secrets
docker service     Manage services
docker stack       Manage Docker stacks
docker swarm       Manage Swarm
docker system      Manage Docker
docker trust       Manage trust on Docker images
docker volume      Manage volumes
```

---

## Agora vamos a pratica

**Informações docker**

Aqui visualizamos todas as informações pertinentes ao docker, como versão, quantidade de imagens, containers e etc.

```
docker info
```

![Docker_info](./imgs/docker_info.png)

---

**Subindo um container**

Para subir um container na mão temos alguns itens essenciais


```
docker container run <parametros> <image>
```

Parametro | descrição
:---:|:---:
`-t` | exibir dados ssh
`-i` | saída iterativa


Esses parametros foram utilizados pois queremos ver os logs da image em tempo real, esses parametros **NÃO** mantem o container rodando.

Na programação é um pratica muito comum começarmos com o "Hello world", aqui não é diferente.

```
docker container run -ti hello-world
```

Agora vamos subir uma image `nginx`.

Parametro | descrição
:---:|:---:
`-d` | mantem o container executando em background
`--name` | definir um nome no container

```
docker container run -d --name servidor_nginx  nginx
```

**Listando** containers para capturar o `CONTAINER ID`.

```
docker container ls
```

**Deletando** containers

Pré requisito tem um `CONTAINER ID`.

Parametro | descrição
:---:|:---:
`rm` | opção para remover container
`-f` | força a remoção, caso em execução

```
docker contaienr rm -f <CONTAINER ID>
```
