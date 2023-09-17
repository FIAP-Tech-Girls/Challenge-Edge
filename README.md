#Desenvolvimento da arquitetura inicial de uma aplicação IoT capaz de receber e transmitir dados provenientes de dispositivos conectados.
##
##Tutorial para auxílio na instalação de um servidor local de IoT “Fiware”
###Primeiro Passo:
    Baixar o software de Virtual Machine -  VMware workstation
###Segundo Passo:
    Baixar uma versão de ISO de distro Linux - Ubuntu Desktop 22.04.3 LTS
###Terceiro Passo:
    Realizar a instalação da imagem na máquina virtual (VM)
###Quarto Passo:
    Instalar o software Postman para comunicação com o nosso servidor.
###Quinto Passo:
    Fazer o download da collection de comandos do Postman no github do Fiware descomplicado disponibilizado pelo professor Fabio Cabrini. https://github.com/fabiocabrini/fiware/blob/main/FIWARE.postman_collection.json
###Sexto Passo:
    Realizar a importação dos arquivos da collection para o Postman para os testes de comunicação com o servidor IoT Fiware. 
###Sétimo Passo:
    Após a instalação do Linux e a sua correta inicialização, abrir um terminal (Ctrl +Alt + T) no caso do Ubuntu e seguir os seguintes comandos:
    (não esquecer de configurar a rede da VM como Bridge para ter acesso a rede)
###Oitavo Passo: (Comandos Linux)
    ##-Instalar  o ifconfig para identificar o IP da máquina virtual, com o comando:
        sudo apt-get install net-tools
    ##-Comando para ler o IP da VM (Virtual Machine), com o comando:
        ifconfig
    -Instalar o git, com o comando:
        sudo apt install git
    -Instalar o docker:
    (O pacote de instalação do Docker disponível no repositório oficial do Ubuntu pode não ser a versão mais recente. Para garantir que tenhamos a versão mais recente, iremos instalar o Docker do repositório oficial do Docker. Para fazer isso, adicionaremos uma nova fonte de pacote, adicionaremos a chave GPG do Docker para garantir que os downloads sejam válidos, e então instalaremos o pacote.)
        Primeiro, atualize sua lista existente de pacotes, com o comando:
         	sudo apt update
        Em seguida, instale alguns pacotes pré-requisito que deixam o apt usar pacotes pelo HTTPS, com o comando:
         	sudo apt install apt-transport-https ca-certificates curl software-properties-common

        Então, adicione a chave GPG para o repositório oficial do Docker no seu sistema, com o comando:
         	curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

        Adicione o repositório do Docker às fontes do APT, com o comando:
            sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"

        Em seguida, atualize o banco de dados do pacote com os pacotes do Docker do recém adicionado repositório, com o comando:
            sudo apt update

        Certifique-se de que você está prestes a instalar do repositório do Docker ao invés do repositório padrão do Ubuntu, com o comando:
            apt-cache policy docker-ce

        Observe que o docker-ce não está  instalado, mas o candidato para a instalação é do repositório do Docker para o Ubuntu 20.04 (focal).
        Finalmente, instale o Docker, com o comando:  
            sudo apt install docker-ce
       
    -Copiar os arquivos do repositório de Fiware Descomplicado, com o comando:
        git clone https://github.com/fabiocabrini/fiware
    -Entrar na pasta do Fiware, com o comando:
        cd fiware
    -Rodar os containers, com o comando:
        sudo docker compose up -d
    -status dos containers, com o comando:
        sudo docker stats
Nono Passo:
    Após a correta inicialização dos containers Docker com a estrutura do Fiware, realizar um teste de “Health Check” dos componentes “IOT Agent MQTT”, “Orion Context Broker” e do “STH - Comet” (em {{url}}, configurar corretamente o IP do seu servidor de IoT).
Décimo Passo:
    Apresentar as respostas dos comandos “Health Check” no Postman dos componentes “IOT Agent MQTT”, “Orion Context Broker” e do “STH - Comet” (em Send, enviar comando e visualizar a reposta Health Check do Orion Context Broker)


Sobre o nosso projeto:

Com o Arduíno/ESP32, iremos melhorar fluxo de carros, utilizando semáforos inteligentes. Além de medir o trânsito em tempo real, integrando com a IA em Python posteriormente, onde haveria um sensor de velocidade e distância, parecido com os que têm nas vias, e um LCD, que avisaria se está ou não congestionado. Com a integração futura, com desenvolvimento web também, enviaria para os usuários outras rotas, justamente a ideia principal do projeto.
