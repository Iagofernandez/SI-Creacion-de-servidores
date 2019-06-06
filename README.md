
Creacion de servidor ssh 

QUE ES UN SERVIDOR SSH?
SSH o también conocido como Secure Shell, es un protocolo y el nombre del programa que lo implementa. SSH es ampliamente conocido por ser el protocolo seguro para la administración remota de servidores, routers, switches y un largo etcétera de equipos. El protocolo SSH permite manejar por completo el servidor o dispositivo de red mediante un intérprete de órdenes, además, también podemos redirigir el tráfico de X para ejecutar programas gráficos a través de la propia sesión SSH.

SEGURIDAD

El cifrado de SSH proporciona autenticidad e integridad de los datos transmitidos por una red insegura como internet.

Utiliza llaves públicas para la autenticación en la máquina remota.

SSH no sólo sirve para usar comandos en máquinas remotas, sino para transferencias de ficheros de forma segura ya sea por SCP o sFTP y servicios de escritorio remoto.

INSTALACIÓN:

Vamos a usar OpenSSH por tanto vamos a instalarlo:

sudo apt-get install openssh-server

COMANDOS A TENER EN CUENTA:

Para editar la configuración del servidor SSH debemos hacer en consola:

sudo nano /etc/ssh/sshd_config


PARA ARRANCAR SERVIDOR:


sudo /etc/init.d/ssh start
PARA PARAR EL SERVIDOR:


sudo /etc/init.d/ssh stop
PARA REINICIAR EL SERVIDOR:


sudo /etc/init.d/ssh restart

Configuración de sshd_config para la máxima seguridad

Cambiar el puerto por defecto del servidor SSH
Por defecto los servidores SSH utilizan el puerto 22 para las conexiones. Es recomendable cambiar este número de puerto, para evitar que bots o cibercriminales puedan intentar iniciar sesión, aunque por sí solo esto no proporciona seguridad, sí podremos pasar desapercibidos a los escaneos masivos desde Internet. Si por ejemplo queremos usar el puerto 22445 debemos poner en el fichero de configuración lo siguiente:

En la parte que pone port 22 se cambia a port 8599 






