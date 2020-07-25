## Hello World Docker
  # Roda e executa uma imagem
    docker run hello-world
  # Ver container rodando
  # container criados e rodadndo
    docker system prune --volumes
  ## container criados mas sem rodar
    docker ps -a
  # Apagando um container
    docker rm CONTAINER_ID
  # Mostrando images
    docker images
  # Apagando images 
    docker rmi IMAGE_ID


## Gerenciamento básico de container
  # Instalando o nginx lastet
    docker run nginx
  # rodando processo em background
    docker run -d nginx
  # Parando um container
    docker stop CONTAINER_ID
  # Iniciando um container
    docker start CONTAINER_ID
  # removendo um container rodando 
    docker rm CONTAINER_ID -f

## Expondo Portas e Nomeando Containers
  # Nomeando um container my_nginx
    docker run -d --name my_nginx nginx:alpine
  # Parando um container usando o nome
    docker stop my_nginx
  # Iniciando um container usando o nome 
    docker start my_nginx
  ## Expondo porta (meu_pc_port:meu_container_port = 8080:80)
    docker run -d --name expond_port -p 8080:80 nginx:alpine
      # => Acesse http://localhost:8080
  
  
