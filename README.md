Ola esta script foi desenvolvida pelo: Fulldev7
Tutorial da script/comandos:Danyew 

Esta script serve para instalar a qemu no seu termux primeiramente instale o ubuntu lxde pelo andronix
ou so siga o tutorial abaixo

primeiro use este comando:

curl https://raw.githubusercontent.com/AndronixApp/AndronixOrigin/master/repo-fix.sh > repo.sh && chmod +x repo.sh && bash repo.sh && pkg update -y && pkg install wget curl proot tar -y && wget https://raw.githubusercontent.com/AndronixApp/AndronixOrigin/master/Installer/Ubuntu20/ubuntu20-lxde.sh -O ubuntu20-lxde.sh && chmod +x ubuntu20-lxde.sh && bash ubuntu20-lxde.sh

e apos isso faça q configuraçao o que e bem facil certo

apos entrar no ubuntu e ver o root@localhost escreva exit e assim ira voltar para o terminal termux apos isso digite:

nano start-ubuntu20.sh

apos o command+=" -b /sdcard" digite enter e cole o comando abaixo

command+=" -b /storage"

apos isto use ctrl + x depois y e enter apos isto digite ./start-ubuntu20.sh apos entrar e aperecer root@localhost
digite

apt install git

apos instalar use o comando abaixo
