# Intro-ao-docker
Introdução ao Docker

## O que é o Docker?
O docker é uma plataforma aberta que foi criada com o intuito de
- Facilitar no desenvolvimento
- Agilizar a implementação
- E a possibilidade de ter aplicações em ambientes isolados

Com o tempo o docker foi abraçado pela comunidade e graças a
- facilidade de gerenciar
- a agilidade para subir um novo ambiente de desenvolvimento
- e a simplicidade de realizar modificações

Tudo isso ajuda muitos **desenvolvedores e syadmins** no seu dia a dia.

## Vantagens

### Vantagens - Principais vantagens
Uma das principais vantagens do uso do Docker é ter um ambiente
- extremamente leve
- isolado e ajudando com projetos legados

Temos a possibilidade de criar diversos conteiners e serem executados simultaneamente.

### Vantagens - Dependências
Podemos ter um gerenciamento de dependência melhor e assim dando a possibilidade de cada contêiner contem as dependências de cada aplicação.

Assim que criamos um projeto podemos facilmente **importar** ou **exportar** , assim podemos subir de forma fácil para um outro ambiente ou até produção.

### Vantagens - Diversas versões
Podemos ter diversos imagens e conteiners para cada versão do projeto.

Depois de criado podemos ter a portabilidade de testar em qualquer ambiente e facilmente ter uma escalabilidade para produção.


## Porque eu devo usar o Docker
Afinal , porque eu devo usar o Docker e mudar o modo de trabalhar hoje?

- Chega de na minha maquina funciona , depois que você criar uma imagem ela vai funcionar perfeitamente em outra maquina de desenvolvimento e até no servidor de produção.

- Para que disponibilizar uma grande documentação de como configurar o projeto se podemos disponibilizar uma imagem e ainda configurar com todas as recomendações de segurança.

- Vamos imaginar que um novo integrante entre na equipe , como o Docker podemos criar um novo ambiente de desenvolvimento em minutos e assim poupando o tempo de desenvolvedor.

- A facilidade para encontrar exemplos , projetos opensource e ver como outros desenvolvedores trabalham.

- Atualmente o Docker está sendo considerada um "idioma" , pois ele auxilia na comunicação entre o código e a infraestrutura.

## Ainda não sei se uso o Docker

### Para o Desenvolvedor
- Só precisa se preocupar em desenvolve uma vez e pode executar em qualquer local.
- Não é necessário se preocupar com dependências ou pacotes.
- Só precisa ter o foco no desenvolvimento.
- Com o Docker é possível ter diversos ambientes para testes.
- Como já foi falado evitamos o clássico **localhost funciona**.

### Para o syadmin
- O responsável pela infraestrutura configura uma vez e executa em qualquer lugar.
- Podemos eliminar incertezas na entrega das aplicações ou serviços.
- Com o Docker temos um ciclo de trabalho mais eficiente e ágil.
- É possível ter uma infraestrutura escalável facilmente.

### Para o usuário
- O Docker instala softwares em um ambiente isolado assim evitando problemas locais.
- Podemos evitar conflitos de múltiplas dependências de pacotes e ter um software especifico para projeto.


## Como a infraestrutura de servidores é projetada

### Antigamente sem o uso da plataforma de containers
Uma infraestrutura sem o uso de containers deixa todo o projeto mais pesado e lento.

Em toda maquina virtual tem um sistema operacional instalado , deixando o projeto muito mais lento , pesado e até aumentando o custo

Diferente do Docker a virtualização precisa de um sistema operacional e podemos ver a imagem abaixo para entender melhor.

!()[images/PARAVIRTUALIZACAO-1.png]
!()[images/VIRTUALIZACAO-1.png]

> A virtualização também pode virar um processo rápido e seguro com o uso de Vagrant.

### Como funciona com o uso de containers
Já com o uso de containers podemos ver que só é necessário obter os binários e as bibliotecas.

!()[images/CONTAINERS-1.png]

O Docker usa um modelo de isolamento utilizado é o virtualização a nível de sistema operacional , esse método de virtualização onde o kernel do sistema operacional permite o processamento de múltiplos processos e esses processos são executados isoladamente no mesmo host.

Esses processos isolados em execução são denominados no Docker de container.

O docker usa uma funcionalidade do kernel denominada de namespaces , ele é responsável por criar ambientes isolados entre os containers e os processos em execução não terão acesso aos recursos de outra.

Para evitar exaustão dos recursos o Docker usa a funcionalidade de cgroups do kernel e ele é responsável por criar limites do uso de hardware a disposição.

## Conhecendo a arquitetura

### Imagens
As imagens podemos entender como formas de bolo ou template usados para criar containers.

As imagens não containers , mais dão base consistente para que aja um container.

Temos imagens oficiais ou criadas pela comunidades.

Podemos armazenar elas localmente usando o Docker Registry ou no Dockerhub

### Containers
Já os containers podemos entender como bolos prontos , não podemos criar um container sem uma imagem previamente.

Os containers contem o necessario para executar uma aplicação e são baseados nas images.

Os mantem o isolamento da aplicação e de recursos.

## Conhecendo o conceito
### Conhecendo o Docker​ ​Engine
O docker engine é um **daemon** , ele é nos auxilia na construção , no envio e para executar nossos containers.

### Conhecendo o Docker Client
Já o Docker client é responsável por receber as entradas do usuário e as enviar para a engine.

Podemos ter um client e o engine na mesma maquina. Porem eles podem ser executados em hosts diferentes.

### Conhecendo o Docker Registry​​
O Docker registry é responsável por armazenar nossas imagens , ele pode ser usado de forma local ou criar o nosso próprio servidor de imagens.

Esse servidor pode ser privado ou publico , um exemplo de servidor publico é o Dockerhub onde podemos encontrar diversas imagens e até subir a nossa.


### Conhecendo o Dockerfile
O dockerfile é um arquivo que auxiliar na criação de uma imagem , basicamente é usado instruções e elas são aplicadas em uma determinada imagem para ue outra imagem seja criada baseada nas modificações.

Mais pra frente vamos aprender como criar nosso arquivo Dockerfile e como podemos subir nossa imagem para o dockerhub.

### Conhecendo o Docker compose
O docker compose é uma ferramenta para nos auxiliar na criação de múltiplos containers Docker , com elas podemos configurar todos os parâmetros necessários para executar um container a partir de um arquivo de definição.

Vamos imaginar que nesse arquivo de execução podemos selecionar definir determinados serviços , podemos setar portas abertas , variáveis de ambiente , volumes , configurar redes e muitas possibilidade que não conseguimos apenas com o Dockerfile.

## Conhecendo comandos basicos do Docker
### Executando comandos
Temos diversos comandos no Docker , aqui não vou conseguir falar sobre todos e para qualquer duvida eu recomendo fortemente o uso da ajuda.
```sh
sudo docker --help
```


### run
O comando **docker run** é usado para iniciar um novo container , podemos ver como usar essa opção
```sh
sudo docker run --help
```

> Primeiro devemos saber como obter uma imagem , ver as imagens e ai vou demostrar como inicar um container.

### pull
O comando **docker pull** é resposavel por obter uma imagem , essa imagem pode ser do DockerHub ou de outro servidor de imagens.

Podemos usar ele da seguinte forma
```sh
sudo docker pull debian
```
> Podemos querer escolher uma terminada tag , senão ele vai baixar a versão latest.

### images
O comando **docker images** é resposavel por listar as imagens que temos em nossa maquina , assim podemos ver qual imagem usar e até qual TAG.

Vamos usar apenas
```sh
sudo docker images
```

### Executando em background
Agora que já sabemos como obter uma imagem e como listar elas vamos executar um container em background.
```sh
sudo docker run -d debian
```

Usamos o **-d** para ele iniciar em background.

### Acesso a shell e excluindo quando sair
Anteriormente vimos como criar um container em background , agora vou mostrar como criar e já ter acesso ao container.

Podemos usar a opção **-it** , essa opção é a **-i** de interative e a **-t** chama um programa unix para ter acesso usando TTY.

Tambem vamos usar o **-rm** , dessa forma ele vai ser removido assim que for usado.
```sh
sudo docker run -it --rm debian
```

### Listando containers
Podemos listar os container que estão em funcionamento usando o **ps** e ele nos ajuda muito para saber quais containers estão em funcionamento.
```sh
sudo docker ps
```

### Passando um nome ao container
Podemos passar um nome ao criar um container , dessa forma podemos passar comandos usando apenas o nome e não o ID.

Podemos criar um nome para ele da seguinte forma
```sh
sudo docker --name "web_server" httpd
```

### Passando uma porta ao container
Vamos imaginar que temos um servidor web em um container , para a porta ficar disponivel podemos usar o **-p80:80** e assim deixamos a porta 80 disponivel em nosso host.
```sh
sudo docker run --name "web_server" -p80:80 httpd
```

> Lembrasse que a primeira é a porta do host e a segunda é a porta do container **-p80:80**.

### Volumes
Vamos realizar mapeamento da seguinte forma.

Primeiro precisamos especificar qual origem do dado no host e segundo onde devemos montar dentro do container.

docker container run -it --rm -v "<host>:<container>" debian


### Portas
Podemos realizar o mapeamento de portas da seguinte forma.

Primeiro precisamos saber qual porta será mapeada no host e qual deve receber essa conexão dentro do container.

Depois de saber podemos realizar o uso da seguinte forma
```sh
docker container run -it --rm -p "<host>:<container>" debian
```

### Recursos (Ram e CPU)
Ao iniciar um container é possivel setar alguns limites na ultilização dos recursos.

Vou falar apenas de
- RAM
- CPU

Podemos setar a quantidade de RAM que vai ser usada passando o **-m**.
```sh
docker container run -it --rm -m 512M debian
```
> O comando acima passamos para o container o uso de 512 MB.

Já para especificar o uso de CPU é ultilizado o uso de pesos para cada container , quanto menor o valor , menor sua prioridade e os pesos podem oscilar de 1 a 1024.
```sh
docker container run -it --rm -c 512 debian
```
> Caso não passe valor para ele , será usado o maior peso possivel e que nesse caso é 1024.
> Para entender melhor sobre vamos imaginer 3 containers , dois deles tem 512 e um 1024. Se os tres processos estiverem funcionando ao mesmo tempo. O primeiro tem 1024 e usará 50% do tempo de processamento e os outros dois processos com peso 512 usarão 25% do tempo de processamento, cada.


### Conhecendo o exec
Depois de criado tambem podemos ter acesso aos nossos containers , para isso vamos usar o exec.

Vamos supor que temos um container com o nome **web_server** e quero ter acesso a ele.

Podemos usar
```sh
sudo docker exec -it web_server
```

### Gerenciando containers
Depois que aprendemos a inserir nome em um container e subir ele para funcionar em background podemos realizar comandos como por exemplo
- stop
- start

Podemos parar um container da seguinte maneira
```sh
sudo docker container stop meu_container
```

Podemos iniciar um container
```sh
sudo docker container start meu_container
```

## Criando a propria imagem
- Revisando imagem e container

Como já vimos anteriormente podemos pesquisar por imagens oficiais no dockerhub.
```sh
https://hub.docker.com/_/php
```

Alem disso podemos tambem usar imagens não oficiais , vamos ver jaja que qualquer um pode criar uma conta e subir a sua imagem personalizada.
```sh
https://hub.docker.com/u/greenmind/
```

Tem todos os projetos temos um **nome** da imagem , o nome podemos colocar o nome do projeto e um exemplo foi o **DB do VidaFacil**.
```sh
https://hub.docker.com/r/greenmind/db_vidafacil/
```

Já as TAGS podemos entender como versão de uma imagem , vou usar como exemplo o repositorio do **Debian** e podemos ver nas tags diversas versões do Debian para uso.
```sh
https://hub.docker.com/_/debian?tab=tags
```

### Criando imagem usando commit
Vamos imaginar ue temos uma imagem em funcionamento , pela imagem ser volaril assim que ela for desligada tudo será apagado e assim todas as modificações serão apagadas.

Podemos usar o commit , criar uma imagem apartir de um container modificado e assim salvar o container com as modificações.

Isso ainda é usado , porem não é uma boa pratica.

No terminal 1 - Vamos criar um container e realizar algumas modificações.
- Vamos usar o Debian
- Vamos instalar o NGINX nele

```sh
sudo docker container run -it --name container_criado debian:9.7 bash
apt-get update
apt-get install nginx -y
exit
```

Depois de sair do terminal - Vamos realizar o commit para criar uma imagem do container , só que antes é preciso parar o container que está em funcionamento e podemos fazer isso da usando o
```sh
sudo docker container stop container_criado
```

Depois podemos realizar o commit para criar a imagem codificada , precisamos passar o nome do container e o nome que queremos da imagem.
```sh
sudo docker commit container_criado "greenmind/debian:nginx"
```

> Podemos ver usando o comando **docker images** a imagem criada.

### Criando imagem com Dockerfile
Antes de criar um Dockerfile é necessario entender algumas instruções , depois de aprender mais sobre essas instruções estaremos prontos e vamos começar a criar o nosso arquivo Dockerfile.

## Entendo instruções
As instruções são passos seguidos pelo Docker , essas instruções são passadas atraves do arquivo Dockerfile e agora vamos entender um pouco sobre eles.

### FROM
A instrução FROM é resposavel por passar o nome da imagem e da tag que vamos usar no arquivo Dockerfile.

Vamos imagem que queremos uma imagem do Debian , podemos passar a seguinte instrução e seguido da TAG e um exemplo seria usar a versão **8** que é o Debian Jessie.
```sh
FROM debian:8
```

> Lembrando que se você passar o nome de uma imagem apenas , será usado a versão latest e isso acontece por padrão.


### MAINTAINER
O maintainer é a instrução resposavel por passar o resposavel por criar a imagem e pode ser usado caso alguem queria relatar algum problema/melhorar imagem.

```sh
MAINTAINER greenmind.sec@gmail.com
```

> Essa instrução não é obrigatoria.

### WORKDIR
O Workdir é um comando que é usado no arquivo Dockerfile , essa instrução nos auxilia na troca de diretorios e podemos usar da seguinte forma.

```sh
WORKDIR /root
```

Dessa forma estamos enviando uma instrução ao docker que desejamos ir para o diretorio **/root**.

> Essa opção pode nos ajudar , dessa forma não precisamos passar comandos como o **cd** e assim seguimos boas praticas.

### COPY
O copy é uma instrução usada para copiar algo para dentro da imagem , por exemplo..

Temos um projeto no github , esse projeto tem os codigos fontes em sua raiz e tambem o arquivo Dockerfile.

Podemos copiar tudo para um diretorio expecifico , vou dar como exemplo a copia dos arquivos locais para o diretorio /application.

```sh
COPY . /application
```

> Dessa forma será **copiado todos os arquivos do diretorio** corrente para o diretorio da imagem **/application**.


### RUN
O comando run é resposavel por passar algum comando como instrução , podemos usar como exemplo uma imagem e queremos atualizar o repositorio dela ou até instalar algo.

Podemos usar o **RUN** para isso e ele funciona da seguinte forma
```sh
RUN apt-get update
```

> Sempre que usar a imagem para instalar algo eu recomendo usar o update.

Outro exemplo é a instalação de algum programa e nunca se esqueça de passar o **-y** para que a instalação seja aceita.
Porque senão tera um erro.
```sh
RUN apt-get install nano -y
```

> Não esqueça de passar o argumento -y , caso não passe a ordem será parada.


### EXPOSE
A instrução EXPOSE é usada para expor uma determinada porta da nossa imagem , vamos imaginar um servidor web , eles costumam funcionar por padrão na porta 80 e devemos passar a porta que queremos usar para o arquivo Dockerfile.

Vamos dar um exemplo e expor a porta **80** local.
```sh
EXPOSE 80
```

### ENTRYPOINT
O entrypoint é um argumento para ser usado caso queira usar sempre um comando ao iniciar o container e veja o exemplo para entender melhor.

Vamos imaginar que temos uma aplicação , queremos executar ela toda vez que o container for iniciado e para isso podemos usar o **ENTRYPOINT**.

> Vou usar como exemplo o NMAP , esse projeto é considerado o melhor portscan do mundo e pode nos auxliar no reconhecimento de aplicações.

Na instrução a baixo é chamado o nmap assim que o container for iniciado.
```sh
ENTRYPOINT ["nmap"]
```

### CMD
A instrução CMD eu vejo ela como um complemento do ENTRYPOINT , vamos imaginar o complemento anterior , onde passamos um programa para o ENTRYPOINT e agora vamos passar o CMD logo a baixo.

Vamos imaginar que eu executei o container , nada foi passado e o que vai acontecer?
Basicamente se nada for passado ele vai executar o CMD , nesse caso ele só está retornando a versão do projeto e em outros casos poderia ser algum comando ou até alerta.

```sh
ENTRYPOINT ["nmap"]
CMD ["--version"]
```

### Entendo a ordem das instruções
As instruções que o nosso arquivo Dockerfile tem , vou usar como exemplo o uso de uma imagem Debian , um servidor NGINX ,vamos expor a porta 80 e por fim realizar o comando para iniciar o NGINX toda vez que iniciar o container.

Nosso arquivo Dockerfile
```sh
FROM debian:9.7
RUN apt-get update
RUN apt-get install nginx -y
EXPOSE 80
EXTRYPOINT[""]
```
> Podemos criar a imagem acima usando o **docker build** , devemos passar um nome , uma tag e onde está o arquivo Dockerfile.
```sh
sudo docker build -t "greenmind/debian:nginx2"
```

Agora se nós fossemos realizar uma modificação , nesse caso vamos inserir um comando acima do comando de instalação do NGINX e podemos ver que tudo a baixo será refeito.
```sh
FROM debian:9.7
RUN apt-get update
RUN apt-get install nano -y
RUN apt-get install nginx -y
EXPOSE 80
EXTRYPOINT[""]
```

> Podemos ver que os passos a baixo serão refeitos e uma outra observação é o uso do **-y** para aceitar a instalação.

## Listando Imagens e Containers

### Listando imagens
Agora que já sabemos como criar as nossas imagem vamos ver como listar elas e ver mais informações sobre nossas imagens.

Antes de tudo vamos aprender a **listar as imagens** , podemos fazer isso facilmente usando
```sh
sudo docker images
```
Ao executar podemos ver as seguintes informações
- REPOSITORY (é o respositorio da imagem , podemos ver o nome e até de onde foi baixado.
> Por padrão é usado o Dockerhub , porem se a imagem foi baixada de outro servidor é possivel ter o endereço na frente do nome

- TAG (Tag é usada para diferenciar uma imagem , podemos seguir as boas praticas e inserir a versão do projeto utilizado)
- IMAGE ID (é o ID unico da imagem e pode ser usado para identificar a maquina assim como o nome.
> ela tambem pode ser identificada pelos 5 primeiros caracteres do ID.

- CREATED (é quando a imagem foi criada)
- SIZE (é o tamanho que a imagem está ocupando)

### Listando containers
Podemos listar container usando a opção **ps**.
```sh
sudo docker ps
```

O resultado são os seguintes
- CONTAINER ID (É o numero unico do container)
- IMAGE (É a imagem usada pelo container)
- COMMAND (Como o container é volatil ele sempre vai precisar de um serviço rodando para manter o container funcionando.
- CREATED (Quando o container foi criado)
- STATUS (Quando o container foi ligado , mostra quando tempo está UP)
- PORTS (pois portas estão expostas)
- NAMES (É o nome dado ao container , por padrão ele sorteia e podemos tambem dar nomes a ele.

## Subindo imagem para o Dockerhub

### Conhecendo o Dockerhub
O dockerhub basicamente é um repositorio publico de imagens , lá podemos encontrar imagens oficiais como por exemplo
- NGINX
- DEBIAN
- MYSQL

Quanto tambem imagens publicas de pessoas , tambem podemos pagar para ter repositorios privados e por padrão temos 1 gratuito.
```sh
https://hub.docker.com/
```

### Criando conta no Dockerhub
Podemos baixar imagens sem ter conta , porem alguma é necessario ter uma conta e podemos criar uma conta em
```sh
https://hub.docker.com/signup
```

### Entendo sobre stars
Stars é uma forma de pontuar reputação de uma imagem , funciona semelhante ao github e quanto mais starts mais bem conceituada é uma imagem.

### Imagem oficial e não oficial
Como eu falei anteriormente é possivel obter imagens oficiais e subir as nossas proprias imagens para o Dockerhub.

Eu vou criar uma imagem que tem como função subir uma API em Node e subir ela para meu dockerhub.

### Subindo imagem para o Dockerhub
Primeiro precisamos ter uma imagem em nossa maquina , depois precisamos estar logados no Dockerhub e depois é só dar o comando **docker push**.
```sh
sudo docker push "greenmind/debian:nginx"
```

Depois disso nossa imagem vai ser inserida na sua pagina do Dockerhub e podera ser usada por qualquer pessoal se estiver publica.

### Obtendo imagem usando pull
Depois de subir nossa maquina para o Dockerhub podemos obter ela usando o comando **docker pull** e tambem precisamos estar logados no dockerhub.

Podemos obter a imagem usando
```sh
sudo docker pull greenmind/debian:nginx
```
