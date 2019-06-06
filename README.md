
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

Port 22445

Bloquear el acceso root en las conexiones remotas
PermitRootLogin no

Configuraciones de seguridad adicionales

Existen otras configuraciones recomendadas para evitar las conexiones no deseadas a nuestro servidor SSH. Estas conexiones son:

LoginGraceTime: Estableceremos el tiempo necesario para introducir la contraseña, evitando que el atacante tenga que «pensar mucho».
MaxAuthTries: Número de intentos permitidos al introducir la contraseña antes de desconectarnos.
MaxStartups: Número de logins simultáneos desde una IP, para evitar que se pueda utilizar la fuerza bruta con varias sesiones a la vez.
AllowUsers: Es crear una lista blanca de usuario. Este parámetro nos permite configurar los usuarios que podrán conectarse. Una medida muy restrictiva pero a la vez muy segura ya que bloqueará todas las conexiones de los usuarios que no estén en el listado. Los usuarios que tengamos aquí podrán conectarse, y el resto no.
DenyUsers: Parecido al anterior, pero ahora creamos una lista negra. Los usuarios que tengamos aquí no podrán conectarse, y el resto sí.
AllowGroups/DenyUsers: Exactamente igual a lo anterior, pero en lugar de crear una lista blanca/negra de usuarios, es de grupos de usuarios.


