# Tech Girls - Projeto IBM - Tiana & Edge Computing

# Sobre o nosso projeto

Com Smart Cities, em uma pesquisa, entendemos que o maior problema que atinge São Paulo e todos que aqui habitam é justamente o trânsito. Então, começamos a pensar em formas de melhorias do trânsito unindo a tecnologia a nosso favor.

## O que faremos, então, para a melhoria do trânsito?

Com Python, criamos uma inteligência artificial chamada Tiana que foca na melhor experiência do usuário e que se comunica diretamente com ele. Cada usuário tem a sua preferência, e além das configurações que o próprio usuário poderá colocar manualmente, a ideia é fazer um machine learning, para que cada usuário tenha uma experiência única. <br>

Para nos auxiliar nesse trabalho, iremos utilizar o ESP32, que conecta a bluetooth e poderíamos, futuramente, fazer uma conexão com a Tiana que avisaria em tempo real se um local está congestionado ou não. Além da própria comunicação com os usuários com a aplicação. E, antes de avançarmos para o tópico que fala melhor sobre os sensores que utilizaremos e o que pretendemos fazer futuramente com o ESP32, acesse ao <a href="https://github.com/FIAP-Tech-Girls/Challenge-Python">repositório da Tiana</a> aqui, para saber mais informações!

## ESP32 e como ele nos auxiliará nesse processo

Os sensores que iremos utilizar são:
<ul>
    <li>Sensores de Infravermelho (IR): Coloque sensores IR em cada faixa de tráfego para detectar veículos.</li>
    <li>Sensores de Ultrassom: Esses sensores podem medir a distância até um objeto, o que pode ser usado para detectar veículos.</li>
</ul>

Além de fazer um cálculo para sabermos se está ou não congestionado, pretendemos utilizar leds para semaforos inteligentes e um fluxo mais inteligente pela cidade, melhorando experiência não somente dos motoristas, como também dos pedestres.

## Como iremos simular?

Iremos fazer uma maquete, para mostrar a banca e nos auxiliar na etapa de testagem, quando tudo estiver pronto. A maquete será em mdf e utilizaremos vários carrinhos com um único destino, e dois caminhos distintos para auxiliar o grupo.

# Challenge de Edge
## O que fizemos nessa primeira etapa da terceira sprint?
Nessa primeira etapa, entendemos como funciona um servidor e como podemos ver se está tudo funcionando corretamente. Segue abaixo o tutorial do que fizemos nessa sprint 3. <br>
*Link do vídeo para tutorial melhor explicado*: https://youtu.be/NZnPXaSQGAM?si=187WFFkXnyoz2EIe
## Tutorial para auxílio na instalação de um servidor local de IoT “Fiware”
### Primeiro Passo:
Baixar o software de Virtual Machine -  VMware workstation
### Segundo Passo:
Baixar uma versão de ISO de distro Linux - Ubuntu Desktop 22.04.3 LTS
### Terceiro Passo:
Realizar a instalação da imagem na máquina virtual (VM)
### Quarto Passo:
Instalar o software Postman para comunicação com o nosso servidor.
### Quinto Passo:
Fazer o download da collection de comandos do Postman no github do Fiware descomplicado disponibilizado pelo professor Fabio Cabrini. https://github.com/fabiocabrini/fiware/blob/main/FIWARE.postman_collection.json
### Sexto Passo:
Realizar a importação dos arquivos da collection para o Postman para os testes de comunicação com o servidor IoT Fiware. 
### Sétimo Passo:
Após a instalação do Linux e a sua correta inicialização, abrir um terminal (Ctrl +Alt + T) no caso do Ubuntu e seguir os seguintes comandos:
    (não esquecer de configurar a rede da VM como Bridge para ter acesso a rede)
### Oitavo Passo: (Comandos Linux)
## -Instalar  o ifconfig para identificar o IP da máquina virtual, com o comando:
    sudo apt-get install net-tools
## -Comando para ler o IP da VM (Virtual Machine), com o comando:
        ifconfig
## -Instalar o git, com o comando:
        sudo apt install git
## -Instalar o docker:
(O pacote de instalação do Docker disponível no repositório oficial do Ubuntu pode não ser a versão mais recente. Para garantir que tenhamos a versão mais recente, iremos instalar o Docker do repositório oficial do Docker. Para fazer isso, adicionaremos uma nova fonte de pacote, adicionaremos a chave GPG do Docker para garantir que os downloads sejam válidos, e então instalaremos o pacote.)
## Primeiro, atualize sua lista existente de pacotes, com o comando:
    sudo apt update
## Em seguida, instale alguns pacotes pré-requisito que deixam o apt usar pacotes pelo HTTPS, com o comando:
         	sudo apt install apt-transport-https ca-certificates curl software-properties-common

## Então, adicione a chave GPG para o repositório oficial do Docker no seu sistema, com o comando:
         	curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

## Adicione o repositório do Docker às fontes do APT, com o comando:
            sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"

## Em seguida, atualize o banco de dados do pacote com os pacotes do Docker do recém adicionado repositório, com o comando:
            sudo apt update

## Certifique-se de que você está prestes a instalar do repositório do Docker ao invés do repositório padrão do Ubuntu, com o comando:
            apt-cache policy docker-ce

## Observe que o docker-ce não está  instalado, mas o candidato para a instalação é do repositório do Docker para o Ubuntu 20.04 (focal).
## Finalmente, instale o Docker, com o comando:  
            sudo apt install docker-ce
       
## -Copiar os arquivos do repositório de Fiware Descomplicado, com o comando:
        git clone https://github.com/fabiocabrini/fiware
## -Entrar na pasta do Fiware, com o comando:
        cd fiware
## -Rodar os containers, com o comando:
        sudo docker compose up -d
## -status dos containers, com o comando:
        sudo docker stats
## Nono Passo:
Após a correta inicialização dos containers Docker com a estrutura do Fiware, realizar um teste de “Health Check” dos componentes “IOT Agent MQTT”, “Orion Context Broker” e do “STH - Comet” (em {{url}}, configurar corretamente o IP do seu servidor de IoT).
## Décimo Passo:
Apresentar as respostas dos comandos “Health Check” no Postman dos componentes “IOT Agent MQTT”, “Orion Context Broker” e do “STH - Comet” (em Send, enviar comando e visualizar a reposta Health Check do Orion Context Broker)
##
