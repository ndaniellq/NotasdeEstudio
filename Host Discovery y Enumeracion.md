# DESCUBRIMIENTO DE HOSTS


> Para hacer descubrimiento de hosts usualmente utilizamos comandos como nmap, arp-scan o netdiscovery, la manera como se utilizan son las siguientes:



## DESCUBRIMIENTO DE HOST CON NMAP


> El comando de NMAP que usualmente utizo para descubrimiento de host es el siguiente:

``nmap -sn -sS --min-rate 5000 -T3 <IP_NET/MASK> -oX <archivo_de_salida.txt>``


> En caso de que el ping este bloqueado uso el comando PS para que le haga una consulta directa al puerto:

``nmap -sn -sS -PS80,443,22,3389,139,445,53,389,21,23 --min-rate 5000 -T3 <IP_NET/MASK> -oX <archivo_de_salida.txt>``



> Aqui algunas otras opciones validas

**-PR**  --> ARP Host Discovery

**-sn**  --> Sin escaneo de puertos

**-n**   --> Sin resolucion de nombres

**-PE**  --> Escaneo con ping ECHO

**-PP**  --> Escaneo con ping timestamp

**-PM**  --> Sirve si el ping esta bloqueado aunque hay otras opciones como el -PS

**-sS**  --> Para evadir el firewall no completando el Three Way Handshake, contrario al -ST que el Full Connect 

**-PA <port>**  --> Envia un ACK vacio esperando un RST a nivel de TCP

**-PU <port>**  --> 

**-PS <port>**  --> Envia SYNC vacios esperando un ACK haciendo un sondeo TCP por defecto por el puerto 80 pero uno mismo puede indicar los puertos, se recomienda poner los puerto mas comunes.

**-sF**  --> TCP FIN

**-sX**  --> TCP Xmas

**-sN**  --> TCP NULL

**-sA**  --> TCP ACK

**--min-rate <numero_de_paquetes>** --> Para optimizar el scaneo indicandole a nmap la cantidad de paquetes minima que debe enviar usualmente uso 5000




## DESCUBRIMIENTO DE HOST ARP-SCAN

> El nombre lo indica


``arp-scan -I <INTERFAZ> <IP_NET/MASK> --ignoredups``



## DESCUBRIMIENTO DE HOST CON NETDISCOVER

> Hace un escaneo de ping sobre toda la red


``netdiscover -i <INTERFAZ> -r <IP_NET/MASK>`` 



# IDENTIFICACION DE SERVICIOS Y SISTEMA OPERATIVO

> Para identificar servicios nos apoyamos en varias herramientas como whatweb, wpscan o drupalscan pero principalmente en NMAP y en sus scripts



## IDENTIFICACION DE SERVICIOS CON NMAP

> Para identificar la version de los servicios usamos la opcion -sV asi:


``nmap -p <PUERTOS> --open -n -sV -Pn <IP_NET/MASK> -oX <archivo_de_salida.txt>``


**-n** --> Para no hacer resolucion DNS

**-sV** --> Para identificacion de la version de los servicios

**-Pn** --> Para que asuma que el host esta activo aunque no responda a ping

**-oX** --> Para que me guarde un archivo con el resultado en la tura especificada



> Para identificar la version del sistema operativo podemos usar la opcion -O --osscan-guess --version-all :

``nmap -p <PUERTOS> --open -n -sV -O --osscan-guess --version-all -Pn <IP_NET/MASK> -oX <archivo_de_salida.txt>``


<n>

> Otra manera de identificar el sistema operativo ya que esa opcion -O no es para nada precisa es a traves de scripts de nmap

### En Windows

``nmap -p <PUERTOS> --open -n -sV -O --osscan-guess --version-all -Pn <IP_NET/MASK> -oX <archivo_de_salida.txt>``

