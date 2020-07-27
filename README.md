# Hello World Docker
  ## Roda e executa uma imagem
    docker run hello-world
  ## Ver container rodando
    docker ps
  ## Container criados mas sem rodar
    docker ps -a
  ## Apagando um container
    docker rm CONTAINER_ID
  ## Mostrando images
    docker images
  ## Apagando images 
    docker rmi IMAGE_ID


# Gerenciamento básico de container
  ## Instalando o nginx lastet
    docker run nginx
  ## Rodando processo em background
    docker run -d nginx
  ## Parando um container
    docker stop CONTAINER_ID
  ## Iniciando um container
    docker start CONTAINER_ID
  ## Removendo um container rodando 
    docker rm CONTAINER_ID -f

# Expondo Portas e Nomeando Containers
  ## Nomeando um container my_nginx
    docker run -d --name my_nginx nginx:alpine
  ## Parando um container usando o nome
    docker stop my_nginx
  ## Iniciando um container usando o nome 
    docker start my_nginx
  ## Expondo porta (meu_pc_port:meu_container_port = 8080:80)
    docker run -d --name expond_port -p 8080:80 nginx:alpine
      # => Acesse http://localhost:8080
  ## Conectando a porta 80 do meu_pc com a port 80 do container
    docker run -d --name expond_port_80 -p 80:80 nginx:alpine
      # => Acesse http://localhost/


# Executando comandos no container
  # Exibindo o container
    docker exec my_nginx uname -a
  # Executando o bash
    docker exec my_nginx bash
  # Interagindo com o bash
    docker exec -it my_nginx bash

# Iniciando com volumes
  ## Básico - Criando um volumes
    docker run -d --name my_nginx -p 8080:80 -v $(pwd):/usr/share/nginx/html nginx
  ## Listando volume
    docker volume ls
  ## Criando um volume
    docker volume create vol_test
  ## Descobrindo comandos
    docker volume --help
  ## Inspecionando volume
    docker volume inspect vol_test
  ## Criando volume apontando o diretório
    docker volume create --driver local --opt type=none --opt device=$(pwd) --opt o=bind volume_name
  ## Usando o volume criado em um novo container
    docker run -d --name nginx2 -p 8081:80 -v volume_name:/usr/share/nginx/html nginx
  ## Matando volume desatachado
    docker volume prune

# Iniciando Networks

