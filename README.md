Ola esta script foi desenvolvida pelo: Fulldev7
Tutorial da script/comandos:Danyew 

Esta script serve para instalar a qemu no seu termux primeiramente instale o ubuntu lxde pelo andronix
ou so siga o tutorial abaixo

primeiro use este comando:

curl https://raw.githubusercontent.com/AndronixApp/AndronixOrigin/master/repo-fix.sh > repo.sh && chmod +x repo.sh && bash repo.sh && pkg update -y && pkg install wget curl proot tar -y && wget https://raw.githubusercontent.com/AndronixApp/AndronixOrigin/master/Installer/Ubuntu20/ubuntu20-lxde.sh -O ubuntu20-lxde.sh && chmod +x ubuntu20-lxde.sh && bash ubuntu20-lxde.sh

e apos isso faça q configuraçao o que e bem facil certo

apos entrar no ubuntu e ver o root@localhost escreva exit e assim ira voltar para o terminal termux apos isso digite:

nano start-ubuntu20.sh

assim que usar este comando ira aparecer varias coisas em sua tela apague tudo e copie o script abaixo e cole no terminal

#!/data/data/com.termux/files/usr/bin/bash
cd $(dirname $0)
## unset LD_PRELOAD in case termux-exec is installed
unset LD_PRELOAD
command="proot"
command+=" --kill-on-exit"
command+=" --link2symlink"
command+=" -0"                                                                           command+=" -r ubuntu20-fs"
if [ -n "$(ls -A ubuntu20-binds)" ]; then                                                    for f in ubuntu20-binds/* ;do
      . $f                                                                                   done                                                                                 fi
command+=" -b /dev"
command+=" -b /proc"
command+=" -b /sys"
command+=" -b /data"
command+=" -b ubuntu20-fs/root:/dev/shm"
command+=" -b /proc/self/fd/2:/dev/stderr"
command+=" -b /proc/self/fd/1:/dev/stdout"
command+=" -b /proc/self/fd/0:/dev/stdin"
command+=" -b /dev/urandom:/dev/random"
command+=" -b /proc/self/fd:/dev/fd"
command+=" -b /data/data/com.termux/files/home/ubuntu20-fs/proc/fakethings/stat:/proc/st>
command+=" -b /data/data/com.termux/files/home/ubuntu20-fs/proc/fakethings/vmstat:/proc/>
command+=" -b /data/data/com.termux/files/home/ubuntu20-fs/proc/fakethings/version:/proc>
## uncomment the following line to have access to the home directory of termux
#command+=" -b /data/data/com.termux/files/home:/root"
command+=" -b /sdcard"
command+=" -b /storage"
command+=" -w /root"
command+=" /usr/bin/env -i"
command+=" MOZ_FAKE_NO_SANDBOX=1"
command+=" HOME=/root"
command+=" PATH=/usr/local/sbin:/usr/local/bin:/bin:/usr/bin:/sbin:/usr/sbin:/usr/games:>
command+=" TERM=$TERM"
command+=" LANG=C.UTF-8"
command+=" /bin/bash --login"
com="$@"
if [ -z "$1" ];then
    exec $command
else
    $command -c "$com"
fi

apos isto use ctrl + x depois y e enter apos isto digite ./start-ubuntu20.sh apos entrar e aperecer root@localhost
digite

apt install git

apos instalar use o comando abaixo
