# Intro-ao-docker
Nesse artigo vou buscar compartilhar uma introdução ao Docker e como podemos usar esse projeto incrível.

## O que é o Docker?
Mas afinal o que é o docker?
Ele é uma plataforma aberta que foi criada com o intuito de- Facilitar na criação de um ambiente de desenvolvimento
- Agilizar a implementação de novos ambientes
- E auxilia na criação de aplicações em um ambiente isolado

Com o tempo o docker foi abraçado pela comunidade e graças a
- Facilidade no gerenciamento
- Agilidade para subir um novo ambiente de desenvolvimento
- A simplicidade de realizar modificações

Tudo isso ajuda muitos **desenvolvedores e syadmins** no seu dia a dia.

## Vantagens
Quais são as vantagens de usar o Docker ?

### Vantagens - Principais vantagens
Uma das principais vantagens do uso do Docker é ter um ambiente
- Extremamente leve
- Isolado e assim ajudando projetos legados

Temos a possibilidade de criar diversos containers e serem executados simultaneamente.

### Vantagens - Dependências
Podemos ter um gerenciamento de dependência melhor e assim dando a possibilidade de cada contêiner contem as dependências de cada aplicação.

Assim que criamos um projeto podemos facilmente **importar** ou **exportar** , assim podemos subir de forma fácil para um outro ambiente ou até para ambientes de produção.

### Vantagens - Diversas versões
Podemos ter diversos imagens e containers para cada versão do projeto.

Depois de criado podemos ter a portabilidade de testar em qualquer ambiente e facilmente ter uma escalabilidade para produção.

## Porque eu devo usar o Docker
Afinal , porque eu devo usar o Docker e mudar o modo de trabalhar hoje?

- Chega de na minha maquina funciona , depois que você criar uma imagem ela vai funcionar perfeitamente em outra maquina de desenvolvimento e até no servidor de produção.

- Para que disponibilizar uma grande documentação de como configurar o projeto se podemos disponibilizar uma imagem e ainda configurar com todas as recomendações de segurança.

- Vamos imaginar que um novo integrante entre na equipe, como o Docker podemos criar um novo ambiente de desenvolvimento em minutos e assim poupando o tempo de desenvolvedor.

- A facilidade para encontrar exemplos , projetos opensource e ver como outros desenvolvedores trabalham.

- Atualmente o Docker está sendo considerada um **idioma** , pois ele auxilia na comunicação entre o código e a infraestrutura. Como algumas pessoas conhecem **infrastructure as code** ou **infraestrutura como código**.

## Ainda não sei se uso o Docker

### Para o Desenvolvedor
- O desenvolvedor só precisa se preocupar em desenvolver uma vez e pode executar em qualquer local.
- Não é necessário se preocupar com dependências ou pacotes.
- Só precisa ter o foco no desenvolvimento.
- Com o Docker é possível ter diversos ambientes para testes.
- Como já foi falado evitamos o clássico **localhost funciona**.

### Para o syadmin
- O responsável pela infraestrutura configura uma vez e executa em qualquer lugar.
- Podemos eliminar incertezas na entrega das aplicações ou serviços.
- Com o Docker temos um ciclo de trabalho mais eficiente e ágil.
- É possível ter uma infraestrutura escalável facilmente.- Conseguimos usar as imagens em processos de CI/CD


### Para o usuário
- O Docker instala softwares em um ambiente isolado assim evitando problemas locais.
- Podemos evitar conflitos de múltiplas dependências de pacotes e ter um software especifico para projeto.- Estudantes de segurança conseguem diversos laboratorios para estudo- Diversos projetos estão usando Docker- Os usuários usar soluções de forma isolada e assim se mantendo mais seguro


## Como a infraestrutura de servidores é projetada

### Antigamente sem o uso da plataforma de containers
Uma infraestrutura sem o uso de containers deixa todo o projeto mais pesado e lento.

Em toda maquina virtual tem um sistema operacional instalado , deixando o projeto muito mais lento , pesado e até aumentando o custo

Diferente do Docker a virtualização precisa de um sistema operacional e podemos ver a imagem abaixo para entender melhor.

!()[images/PARAVIRTUALIZACAO-1.png]
!()[images/VIRTUALIZACAO-1.png]

> A virtualização também pode virar um processo rápido e seguro com o uso de **Vagrant**.

### Como funciona com o uso de containers
Já com o uso de containers podemos ver que só é necessário obter os binários e as bibliotecas.

!()[images/CONTAINERS-1.png]

O Docker usa um modelo de isolamento utilizado é o virtualização a nível de sistema operacional, esse método de virtualização onde o kernel do sistema operacional permite o processamento de múltiplos processos e esses processos são executados isoladamente no mesmo host.

Esses processos isolados em execução são denominados no Docker de container.

O docker usa uma funcionalidade do kernel denominada de namespaces , ele é responsável por criar ambientes isolados entre os containers e os processos em execução não terão acesso aos recursos de outra.

Para evitar exaustão dos recursos o Docker usa a funcionalidade do **cgroups** do kernel e ele é responsável por criar limites do uso de hardware a disposição.

## Conhecendo a arquitetura

### Imagens
As imagens podemos entender como formas de bolo ou template usados para criar containers.

As imagens não containers, mais dão base consistente para que aja um container.

Temos imagens oficiais ou criadas pela comunidades.

Podemos armazenar elas localmente usando o **Docker Registry**,  **Dockerhub**, ou até **Gitlab Registry**.

### Containers
Já os containers podemos entender como bolos prontos, não podemos criar um container sem uma imagem previamente.

Os containers contem o necessário para executar uma aplicação e são baseados nas **imagens**.

Os mantêm o isolamento da aplicação e de recursos.

## Conhecendo o conceito
### Conhecendo o Docker Engine
O **docker engine** é um **daemon** , ele é nos auxilia na construção, no envio e para executar nossos containers.

### Conhecendo o Docker Client
Já o **Docker client** é responsável por receber as entradas do usuário e as enviar para a engine.

Podemos ter um client e o engine na mesma maquina. Porém eles podem ser executados em hosts diferentes.

### Conhecendo o Docker Registry
O **Docker registry** é responsável por armazenar nossas imagens, ele pode ser usado de forma local ou criar o nosso próprio servidor de imagens.

Esse servidor pode ser privado ou publico, um exemplo de servidor publico é o **Dockerhub** onde podemos encontrar diversas imagens e até subir a nossa.


### Conhecendo o Dockerfile
O dockerfile é um arquivo que auxiliar na criação de uma imagem , basicamente é usado instruções e elas são aplicadas em uma determinada imagem para que outra imagem seja criada baseada nas modificações.

Mais pra frente vamos aprender como criar nosso arquivo Dockerfile e como podemos subir nossa imagem para o dockerhub.

### Conhecendo o Docker compose
O docker compose é uma ferramenta para nos auxiliar na criação de múltiplos containers Docker, com elas podemos configurar todos os parâmetros necessários para executar um container a partir de um arquivo de definição.

Vamos imaginar que nesse arquivo de execução podemos selecionar definir determinados serviços , podemos setar portas abertas, variáveis de ambiente, volumes, configurar redes e muitas possibilidade que não conseguimos apenas com o Dockerfile.
## ConclusãoNesse artigo compartilhamos um pouco do que é o Docker, vantagens do uso, como desenvolvedores e sysadmin podem ser beneficiados com o uso dessa incrível tecnologia.

Nos proximos passos vamos explicar como podemos instalar o Docker, criar nosso arquivo Dockerfile, instalar o docker-compose e muitas coisas. Esse é só a **parte 1** de **3 partes**.

Qualquer duvida deixe um comentário que vou buscar responder o mais rápido possível e ajudar a solucionar suas duvidas.
