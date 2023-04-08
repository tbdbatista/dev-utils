# Docker Commands :us:

### Flags
-ti => used to allocate a pseudo-tty and enable interactive communication with the container's command line

-d => used to run a container in detached mode. This means that the container will run in the background, and you will not be attached to its console or terminal

-v ou --volume => used to create a volume or mount a directory from the host machine into the container

-p => used to map a network port on the host machine to a network port inside the container

### Downloading a container image:
docker pull ubuntu:tag => downloads the image with the specified tag.

### Running a container:

docker run ubuntu => runs a container from the image named ubuntu.

docker stop [id] => stops a running container.

docker run -it ubuntu => runs a container in the background.

docker run -dti --name container-name ubuntu => runs a container in the background with the specified name.

### Running applications in containers:

docker run -dti ubuntu => starts a container.

docker exec -it [id or name] /bin/bash => executes bash in the container (can also be executed by just typing "bash").

### Removing containers and images:

docker rm [id] OR [name] => removes a container with the specified ID (can use only the first 3 digits of the ID) or name.

docker rmi [image] => removes the image with the specified name.

### Copying files between the container and the server:
docker cp file-name.extension [container name]:/destination-folder/ => copies the chosen file from the server to the container.

docker cp [container name]:/destination-folder/file-name.extension destination-file-name.extension => copies the chosen file from the container to the server.

### Creating a MySQL container:

1. docker pull mysql:tag.
2. docker run -e MYSQL_ROOT_PASSWORD=Password --name container-name -d -p 3306:3306 mysql:tag => creates a container with the specified name, and the configuration variables set to password for root user and port 3306.
3. docker exec -it container-name bash => executes bash.
4. mysql -u root -p --protocol=tcp => command executed inside the container to open the MySQL server with the TCP protocol.

### Accessing an external docker

docker run -e MYSQL_ROOT_PASSWORD=Senha --name mysql-A -d -p 3306:3306 --volume=/data:/var/lib/mysql mysql => this will start a docker container named "mysql-A" with a MySQL database and map the container's port 3306 to the host's port 3306

mysql -u root -p --protocol=tcp --port=3306 => this command will allow you to access the MySQL shell as root user

### Managing volumes
docker volume create [volume name] => used to create a new volume

docker volume ls => list all the volumes in Docker

docker volume inspect [volume name] => inspect the details of a specific volume in Docker

docker volume rm [volume name] => remove a specific volume from Docker

docker volume prune => remove all unused volumes in Docker

docker run -v [volume name]:[container directory] [image name] => used to mount a volume to a specific directory in a container when running it


### Managing networks

docker network create [network name] => create a new user-defined network in Docker

docker network ls => list all the networks in Docker

docker network inspect [network name] => inspect the details of a specific network in Docker

docker network rm [network name] => used to remove a specific network in Docker

docker network connect [network name] [container name] => used to connect a container to a specific network

docker network disconnect [network name] [container name] => used to disconnect a container from a specific network

docker network prune => remove all unused networks in Docker



### Processing management

docker stats [network name] => display consumption data for the specified container

docker uptade [network name] -m 128M --cpus 0.2 => update the memory usage limit to 128MB and CPU usage to 20% for the specified container. These values can also be set when running the container with the \'docker run\' command

### Server and container information

docker info => display information about containers, images, operating system, architecture, memory, CPU, and other system information

ip a => display information about the server's IP addresses

docker container logs [network name] => display execution logs for the specified container

docker container top [network name] => display the processes running in the specified container

docker network ls => lista as redes utilizadas pelo docker

docker network inspect bridge => indica quais containers estão adicionados a rede bridge

### Creating a Docker Image

1. Create a Dockerfile that defines the instructions to build the image.
2. Open a terminal or command prompt and navigate to the directory that contains the Dockerfile.
3. Run the command "docker image build 'flags' -t [image name]:[tag] [build directory]" with the appropriate options to create the image.
4. Docker will execute each instruction in the Dockerfile.
5. When the build process is complete, Docker will create a new image with the specified name and tag.

#### Flags used:

-t => to specify the name and tag of the new image.

-f => to specify the name and location of the Dockerfile (if it's not called "Dockerfile" or not located in the current directory).

--no-cache => to prevent Docker from using cached layers during the build process.


# Comandos para Docker :brazil:

### Flags
-ti => aloca um pseudo-tty e habilita a comunicação interativa com a linha de comando do container

-d => executa um container no modo desanexado. Isso significa que o container será executado em segundo plano

-v ou --volume => usado para criar um volume ou montar um diretório da máquina host no container

-p => usado para mapear uma porta de rede na máquina host para uma porta de rede dentro do container

### Baixando a imagem de um container
docker pull ubuntu:tag => realiza o download da imagem com a tag citada

### Executando um contâiner
docker run ubuntu => executa um container a partir da imagem com o nome ubuntu

docker stop [id] => para a execução de um container

docker run -it ubuntu => executa um container em segundo plano

docker run -dti --name nome-do-container ubuntu => executa um container em segundo plano com o nome citado

### Executando aplicações no containers
docker run -dti  ubuntu => inicia um container

docker exec -it [id ou nome] /bin/bash => executa o bash no container (também pode ser executado digitando somente bash)

### Remover containers e imagens
docker rm [id] OR [name] => remove um container com a id (pode utilizar somente os 3 primeiros digitos da id) ou com o nome citado

docker rmi [imagem] => remove a imagem com o nome citado

### Copiando arquivos entre o container e o servidor
docker cp nome-do-arquivo.extensao [nome do container]:/pasta de destino/ => copia o arquivo escolhido do servidor para o container

docker cp [nome do container]:/pasta de destino/nome-do-arquivo.extensao  nome-do-arquivo-destino.extensao => copia o arquivo escolhido co container para o servidor

### Criando um container MySQL
1. docker pull mysql:tag
2. docker run -e MYSQL_ROOT_PASSWORD=Senha --name nome-do-container -d -p 3306:3306 mysql:tag => cria o container com o nome excolhido com a configuração das variáveis: senha para usuário root e porta 3306
3. docker exec -it nome-do-container bash => executa o bash
4. mysql -u root -p --protocol=tcp => comando executado dentro do container para abrir o servidor MySQL com o protocolo tcp

### Acessando um docker externamente
docker run -e MYSQL_ROOT_PASSWORD=Senha --name mysql-A -d -p 3306:3306 --volume=/data:/var/lib/mysql mysql => inicia um container do docker nomeado \"mysql-A\" com o MySQL database e mapeia a porta 3306 do container 3306 com a porta 3306 do host

mysql -u root -p --protocol=tcp --port=3306 => concede acesso ao shell do MYSQL como usuário root

### Gerenciando volumes
docker volume create [nome do volume] => cria um novo volume no Docker

docker volume ls => lista todos os volumes no Docker

docker volume inspect [nome do volume] => inspeciona os detalhes de um volume específico

docker volume rm [nome do volume] => remove um volume específico do Docker

docker volume prune => remove todos os volumes não utilizados no Docker

docker run -v [nome do volume]:[diretório do container] [nome da imagem] => é usado para montar um volume em um diretório específico em um container durante a execução

### Gerenciamento de redes

docker network create [nome da rede] => cria uma nova rede definida pelo usuário no Docker

docker network ls => é usado para listar todas as redes no Docker

docker network inspect [nome da rede] =>  é usado para inspecionar os detalhes de uma rede específica no Docker

docker network rm [nome da rede] =>  remove uma rede específica no Docker

docker network connect [nome da rede] [nome do container] => é usado para conectar um container a uma rede específica

docker network disconnect [nome da rede] [nome do container] => desconecta um container de uma rede específica

docker network prune=> é usado para remover todas as redes não utilizadas no Docker

docker run --network [nome da rede] [nome da imagem] => cria um container conectado a rede indicada

### Gerenciamento de processamento

docker stats [nome do container] => indica dados de consumo de processamento do container

docker uptade [nome do container] -m 128M --cpus 0.2 => atualiza o limite de uso da memória para 128M e uso da cpu para 20%, esses valores podem ser setados no \'docker run\'

### Informações do servidor e seus containers

docker inspect [nome do container] => mostra todas as informações do container

docker info => informações sobre containers, imagens, SO, arquitetura, memória, cpu, entre outras informações

ip a => informações sobre os endereços do servidor

docker container logs [nome do container] => informações dos logs de execução 

docker container top [nome do container] => processos em execução no container

docker network ls => lista as redes utilizadas pelo docker

docker network inspect bridge => indica quais containers estão adicionados a rede bridge

### Criando uma imagem para o docker
1. Crie um Dockerfile que defina as instruções para construir a imagem.
2. Abra um terminal ou prompt de comando e navegue até o diretório que contém o Dockerfile.
3. Execute o comando \"docker image build \'flags\' -t [nome da imagem]:[tag] [diretório de criação]\" com as opções apropriadas para criar a imagem.
4. O Docker executará cada instrução no Dockerfile.
5. Quando o processo de build estiver concluído, o Docker criará uma nova imagem com o nome e a tag especificados.

#### flags utilizadas:

-t => para especificar o nome e a tag da nova imagem.

-f => para especificar o nome e a localização do Dockerfile (se ele não se chamar "Dockerfile" ou não estiver localizado no diretório atual).

--no-cache => para impedir que o Docker use camadas em cache durante o processo de construção.
