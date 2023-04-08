# Docker Commands :us:

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

### Processing management
docker stats [nome do container] => display consumption data for the specified container
docker uptade [nome do container] -m 128M --cpus 0.2 => update the memory usage limit to 128MB and CPU usage to 20% for the specified container. These values can also be set when running the container with the \'docker run\' command

### Server and container information
docker info => display information about containers, images, operating system, architecture, memory, CPU, and other system information
ip a => display information about the server's IP addresses
docker container logs [nome do container] => display execution logs for the specified container
docker container top [nome do container] => display the processes running in the specified container



# Comandos para Docker :brazil:
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

### Gerenciamento de processamento
docker stats [nome do container] => indica dados de consumo de processamento do container
docker uptade [nome do container] -m 128M --cpus 0.2 => atualiza o limite de uso da memória para 128M e uso da cpu para 20%, esses valores podem ser setados no \'docker run\'

### Informações do servidor e seus containers
docker info => informações sobre containers, imagens, SO, arquitetura, memória, cpu, entre outras informações
ip a => informações sobre os endereços do servidor
docker container logs [nome do container] => informações dos logs de execução 
docker container top [nome do container] => processos em execução no container

