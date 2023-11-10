SRI - Práctica 1.2 - DNS Linux

Objetivos:

-- Utiliza una máquina virtual Ubuntu.
-- Instalar bind9 con apt.
-- Configura las zonas del DNS igual que en docker.
-- Comprueba (en el propio servidor) con el comando 'dig' que el servidor funciona.


Utiliza una virtual Ubuntu:

Simplemente descargamos una ISO de ubuntu ( en mi caso la versión 22.04 ) y hacemos la instalación desde VirtualBox. No tardas ni 10 minutos en acabar este paso.


Instalar bind9 con apt:

Para instalar bind9 desde la terminal tendremos que usar un comando que se puede encontrar fácilmente en internet. 

sudo apt install bind9

Es recomendable hacer un apt update antes de instalar el bind9 para que no haya problemas.
Para ver si está funcionando correctamente, usaremos el comando systemctl status bind9 y tendremos que comprobar si se está ejecutando. Debe poner “running”.


Configura las zonas del DNS:

Antes de continuar con este apartado, tendremos que comprobar que la máquina Linux que estamos usando tiene la misma dirección IP que el host. A partir de aquí, tendremos que modificar los directorios /etc/bind y /var/lib/bind.

En el /etc/bind tenemos que modificar los archivos de configuración. Por lo tanto cogemos y copiamos los archivos de la práctica anterior de DNS y los pegamos en los archivos correspondientes.

En /var/lib/bind tendremos que crear una base de datos para luego comprobar si funciona el DNS con el comando dig. Podemos coger la DB de la práctica anterior también.

Para acabar de configurar, tendremos que cambiar a adaptador puente y comprobar desde la terminal con el comando netstat -ptan si el puerto está puesto en el predeterminado ( puerto 53 ).


Comprobar funcionamiento con dig:

Para finalizar, usaremos el comando dig @[IP] www.asircastelao.int. y nos debería devolver la IP correspondiente a la que hemos puesto en la base de datos.
