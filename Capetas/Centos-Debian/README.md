![](https://webtematica.com/sites/default/files/styles/790px/public/blog-img/servidores-web.jpg?itok=PXBE6Ehg&timestamp=1452631683)  


# Pasos y comandos importantes para tener siempre en cuenta:

 Verficiar si el hardware, (En especial la tarjeta gráfica), es compatible con cada distribución, y saber si los drivers fueron desarrollados con software libre, código abierto. Ubuntu y CentOS tienen drivers de software privativo. Si es compatible en RedHat, también es compatible en CentOS.
    


  * [Centos Hardware List](https://wiki.centos.org/es/AdditionalResources/HardwareList)

  * [Ubuntu server certificacion](https://certification.ubuntu.com/server)



   * [Debian releases](https://www.debian.org/releases/etch/i386/ch02s01.html.en)


   * [Debian unofficial con algunos drivers con código privativo](https://cdimage.debian.org/cdimage/unofficial/non-free/firmware/)

    Por seguridad no es recomendable instalar aplicaciones que no formen parte de un repositorio o de la tienda oficial, en caso de que un programa externo ocacione problemas, no sera parte de la garantia.

La interfaz gráfica en un sistema operativo, aumenta los focos de inseguridad en el.

A la hora de instalar, se recomienda hacer las particiones manualmente, y tener en cuenta cual es conveniente utilizar, y que tamaños darles. Por ejemplo si es para un servidor web, se recomienda que la partición mas grande sea la de ***/var***.

Cuando el instalador pregunte si deseas configurar el gestor de paquetes, lo recomendable es elegir Estados Unidos, ya que  que en otros paises tardan mucho en actualizarse.

Tener en cuenta con el ***administrador de las IP***, que ip esta libre para nuestro equipo. También tener en cuenta que si compartimos datos con la comunidad de Debian en un ambiente de producción, estariamos gastando ancho de banda.

## Terminal y consola
La ***terminal*** se encarga de llamar a la ***consola***, la consola, es un interprete de comandos, y al mismo tiempo es un lenguaje de programación.

Un tipo de consola es la ***sh***, aunque en general también se utiliza ***bash***. La diferencia entre una consola y otra son los comandos y las variables que manejan. 

La ***consola***, también llamada ***cli o command line interface***, es aquella interface por línea de comandos que me permite interactuar con el sistema, y cada consola tiene sus funciones independientes, lo mismo con las diferentas terminales. 


## Man: Obtener ayuda e información sobre un comando SIN TENER ACCESO A INTERNET

Cuando no tenemos internet y necesitamos ayuda, en Linux los comandos tienen su propia ayuda, por ejemplo: 

* ***file --help***, automáticamente muestra ayuda sobre el comando, y las diferentes opciones que tiene el comando, quien lo escribe, la licencia, los bugs, ejemplos. Para cada comando exites su propio manual, este puede cambiar dependiendo de cada comando. 

* ***man info*** nos indica que para desplazarse entre la página manual de ayuda, utilizar los botones hacia arriba y hacia abajo, tambien hacia los lados. La letra ***q*** es para salir. 

Para buscar una palabra dentro del manual, se utiliza ***/palabra***, esto nos muestra cuales palabras coinciden dentro de la ayuda del comando, tocando ***n*** nos sigue muestra cuales palabras coinciden, y con ***N***, regresa a las que coinciden anteriormente.

***MAN(1)*** es un mensaje que nos indica en que nivel se esta buscando, los distintos niveles son para distintas funciones, el ***nivel 1***, hace referencia a los ejecutables y los comandos, el ***nivel 5***, hace refencia a los archivos.

* ***man -k passwd***, trae todos los comandos, referencias, o archivos, que tengan página manual sobre la palabras 
***passwd***.

* ***man -f passwd***, busca de forma exacta, es una manera también de obtener información de  que comando tengo que utilizar.

* ***man 5 passwd***, busca en el nivel 5, el archivo de configuración passwd.

* ***apropos pass***, es muy similar a lo que seria la opción ***k*** el manual.

## Apagar y reinciar el sistema
En Linux es recomendable reiniciar un servicio, y no reiniciar todo el servidor.

* ***init 0*** // Es el nivel mas bajo del sistema, "Apáguese", mata las conexiones y apaga bruscamente el sistema. Solo se recomienda en casos extremos.

* ***halt*** // Hasta que no termina los procesos no se apaga

* ***shutdown -h +60 "Esto se va a descontrolar"*** // Te da tiempo para cancelar el apagado del sistema, la ***h*** hace referencia a ***halt***.

* ***shutdown -c*** // Cancela el apagado

* ***poweroff*** 

Todos ejecutan ***init 0***, pero apagan adecuadamente el sistema.


* ***shutdown -r***// Reinicia el sistema
* ***reebot***
* ***init 6*** // Reinicia el sistema bruscamente



## System D
Unifica herramientas, y posee mejoras en el arranque del sistema, unifico las distribuciones en una misma herramienta.

No puede ser utilizado en otro sistema que no sea basado kernel de Linux, no es un estandar, por ejemplo en Unix, a diferencia de init, que es un demonio principal de gestión de arranque y de procesos en varios sistemas.

Tiene comandos útiles para, arranque del sistema, gestión de servicios, gestión del sistema, y gestión de registros.


## Utilizar alias
La definición de un alias es renombrar una línea de comandos, por otra, por ejemplo  ***el alias de Diego Armando Maradona, es d10s***.

***alias*** // Muestras los alias creados
***alias ls='ls color=auto'***// Crea un alias para ***ls***
***alias update='sudo apt-get update && sudo apt-get upgrade'*** // Crea un alias, pero si cierro la sesión el alias se borra

***nano .bashrc*** // Abre el editor nano el archivo bashrc del usuario, buscar en donde dice ***some more alias***, y escribir el alias sin ***#***, entonces no se va a perder luego de cerrar la sesión.


## Conocer el estado del sistema

* ***lshw*** // obtiene información desde el sistema  * ***dmidecode***// obitene información directamente desde la bios
* ***lshw*** // Información del sistema    
* ***dmidecode*** // Información del sistema    
* ***lshw -C cput*** // Información sobre el CPU  
* ***lshw -C memory*** // Información sobre la memoria RAM  
* ***dmidecode | head -50*** // Las primeras 50 líneas  
* ***free*** // Cuanta memoria RAM en bytes tengo  
* ***free -h*** // Cuanta memoria RAM en Gb tengo  
* ***lspci*** // Lista los dispositivos PCI buses hay disponibles en el sistema 
* ***id*** // Muestra en que grupo y usuario pertenesco  
* ***group*** // A que grupo pertenezco  
* ***w*** // Muestra quienes estan conectados  
* ***who*** // Muestra a que hora se conecto cada usuario   
* ***uptime*** // Muestra hace cuanto fue encendido el sistema  
* ***whoami***  // Quien soy yo   
* ***top***  // Gestor de procesos  
* ***last***  // Últimas conexiones satisfactorias en el sistema  
* ***lastb***  // Últimas conexiones rechazadas (SE RECOMIENDA SEMANALMENTE PARA EVIDENCIAR ATAQUES)  
* ***vmstat***  // Uso de memoria en tanto a los buffers  
* ***ip addr***  // Muestra los adaptadores de red del sistema  
* ***ip route***  //  Muestra las rutas del sistema 
* ***route -e***  //  Muestra las rutas del sistema 
* ***ip link***  // El estado de un enlace
* ***netstat -n*** // Conexiones en el momento  
* ***netstat -nt*** // Conexiones en el momento con protocolo tcp  
* ***netstat -nu*** // Conexiones en el momento con protocolo udp  
* ***ss*** // Muestra las conexiones, pero mas enfocado a sockets, informa que tipos de conexiones estoy utilizando, por ejemplo http, https  
* ***dmesq*** // Da toda la información correspondiente a los dipositivos de arranque, red, disc duro, librerias, etc. Log de arranque del sistema, solo guarda el último inicio del kernel.      
* ***ps*** // Información de los procesos utilizados por el usuario 
* ***ps -aux*** // Es lo mismo que el top, pero muestra todos los procesos que estan ejecutandose  
* ***pstree*** // Más detallado, procesos en arquitectura de árbol 
* ***df -h*** // Muestra el tamaño del disco duro  
* ***lsblk*** //  Muestra el tamaño del disco duro en forma de árbol
  
## Comando find  
Es mas poderoso que un buscador gráfico, nos permite buscar por fechas, modificaciones, accesos, múltiples características de un archivo, es muy complejo y completo.

* ***find . -name a.@*** // Que busque donde estoy parado y coincidan con el nombre exacto y con cualquier extensión, @ es *.  
* ***find -name [Aa].@*** //   
* ***find -name [Aa][A-Z].@*** //   
* ***find . -iname A.@*** //  Que busque donde estoy parado y el nombre sea inexacto, y con cualquier extensión, @ es *.   
* ***find /home/soporte --type d*** // Busca en soporte los archivos de tipo directorio  
* ***find /home/soporte --type d | grep Descargas*** //  Solamente me busque directorios en Descargas  
* ***find /home/soporte --type d -name D@*** // Solamente me busque directorios que comiencen exactamente con D  
* ***find /home/Descargas -type f -size +1M*** // Que me busque en descargas todo del tipo archivo que pesen mas de 1 Mb   
* ***find /home/Descargas -type f -size +1M -exec ls -lah {} \;*** //  Que me busque en descargas todo del tipo archivo que pesen mas de 1 Mb, y me ejecute ls -lah
* ***find /home/Descargas -type f -size +1M -exec du -hs {} \;*** //  Que me busque en descargas todo del tipo archivo que pesen mas de 1 Mb, y me ejecute du -hs
* ***find . -inum 4457184*** // Busca un archivo por su inodo, es bueno cuando el nombre tiene algún caracter especial.  
* ***find . -inum 4457184 -exec rm -rf {}\;*** // Busca y borra el archivo conflictivo por su inodo  
* ***find /home/soporte/ -mtime -5*** // Buscar archivos modificados hace menos de 5 días. 


## Wget y curl
Sirven para descargar archivos, o obtener información desde un sitio web. Por defecto no vienen instalados. Sin necesidad de tener un navegador web
 
* ***wget url*** // Descarga el archivo de la URL  
* ***wget -c url*** // Continua desde donde quedo la descarga si fue cancelada  
* ***curl -O url*** // Descarga el archivo desde la URL  
* ***wget -c -r -A.iso url*** // Descarga todos los archivos .iso del la url, si se ***-c*** cancela continua, y descargar de forma recursiva ***-r*** en todos los directorios  
* ***wget -c -b -r -A.iso url*** // Descarga todos los archivos .iso del la url, si se ***-c*** cancela continua, y descargar de forma recursiva ***-r*** en todos los directorios, con ***-b*** se ejecutara en background  
* ***tail wget-log*** // Muestra como se esta descargando en background  
* ***curl www.google.com*** // Muestra el contenido de la página de Google 

## Comando history  
Guarda historial de hasta 1000 comandos que halla utilizado, no es recomendable tener tanto historial, lo mejor es hasta máximo 1000, si se puede menos mucho mejor. El problema es que no guarda las fechas  de cuando se ejecuto el comando, y eso para una auditoria es importante.

* ***nano .bashrc*** // Muestra el tamaño de mi history  en * ***HISTSIZE=1000***  
* ***history*** // Muestra el historial de comandos  
* ***history -c*** //  Hace un clear, borra los comandos de history 
* ***nano .bash_logout*** // Muestra los comandos que queremos que se ejecuten cuando salga de la shell  
* ***echo "HISTTIMEFORMAT='%F %T : '" >> .bashrc*** // Ahora mi history va a mostrar la fecha y el tiempo que se ejecuto el comando, eso lo guarda en .bashrc  
* ***!numeroComando*** // Ejecuta un comando del history  
* ***ctrl+r*** // Intenta autocompletar el comando desde history  

## Comando DD
Nos permite sobreescribir un disco duro, o crear una imagen USB.
Es un comando que nos permite escribir bloques, vaciar discos duros, o dar un formato bajo nivel, escribiendo todos los sectores, generar una doble escritura del mismo.

* ***f disk -l*** // Lista todos los dispositivos de almacenamiento conectados  
* ***sudo dd if=/dev/zero of=/dev/sdc bs=512 count=1024*** // Utilizando el archivo especial zero, escritura a bajo nivel, luego el nombre de la unidad USB a formatear, luego se indica el tamaño del bloque, (512 bytes), y por último la cantidad de veces que se escribe el bloque. De esta forma solo se destruye el primer bloque

* ***sudo dd if=/dev/zero of=/dev/sdc bs=512*** // Utilizando el archivo especial zero, escritura a bajo nivel, luego el nombre de la unidad USB a formatear, luego se indica el tamaño del bloque, (512 bytes), y por último la cantidad de veces que se escribe el bloque. De esta forma solo se destruye todo el contenido de todos los sectores de la USB a zero.

* ***sudo dd if=Debian.iso of=/dev/sdc*** // Crea una USB para instalar Debian, desde la imagen .iso descargada.  

# Editor de textos Nano
Es el mas fácil de utilizar, debido a que es el más parecido a utilizar un editor de texto en un entorno gráfico. Límitado a comparación de VIM.

* ***nano*** // Crea un archivo en blanco  

# Editor de texto VIM  
Se encuentra en todas las distribuciones basadas en Unix.
Hay tres modos, comando, inserción, y en modo línea de comandos.
  
* ***vi a*** // Abre un nuevo archivo llamado ***a***    
* ***esc*** // Al presionar esc y en mayúscula ZZ cierra sin guardar    
* ***i*** // Permite comenzar a insertar datos     
* ***a*** // Insertar texto al final de la palabra  
* ***A*** // Insertar datos al final de la línea  
* ***I*** // Insertar datos al principio de la línea 
* ***O*** // Insertar datos en una nueva línea 
* ***:w*** // Guarda el archivo  
* ***:zz*** // Guarda el archivo  
* ***:!q*** // Salir sin guardar  
* ***:!wq*** // Guardar y salir  
* ***h*** // Izquierda    
* ***j*** // Abajo 
* ***k*** // Arriba   
* ***l*** // Derecha
* ***0*** // Primra línea del archivo
* ***$*** // Última línea del archivo
* ***w*** // Desplazarse entre palabras 
* ***ctrl+f*** // Página hacia adelante   
* ***ctl+b*** //  Página hacia atrás  
* ***G*** // Última línea del archivo    
* ***3G*** // Se desplaza hacia la línea 3    
* ***x*** // Elimina la letra    
* ***X*** // Elimina el carácter anterior   
* ***r+letra*** // Reemplaza el carácter donde estoy posicionado   
* ***d+w*** // Elimina una palabra   
* ***D*** //  Elimina la línea desde el carácter hacia la derecha   
* ***d+$*** // Elimina la línea desde el carácter hacia la derecha       
* ***d+f+d*** // Borra el contenido hasta la letra ***d***     
* ***u*** //  Retrocede 1 vez en el tiempo   
* ***:u5*** // Retrocede 5 veces en el tiempo    
* ***/palabra*** // Busca la palabra
* ***?palabra*** // Busca la palabra  
* ***/systemd.@*** // Busca la palabra systemd con algo adelante por ejemplo  ***:, /***   
* ***/[aA].@[lL]*** // Busca un término que coincida con este, empieza con aA, le sigue cualquier cosa, y termina con lL  
* ***:1,$s/Palabra/Leandro/g*** // Desde la primera línea, hasta la última, que me haga una busqueda de todo lo que coincida con  ***Palabra***, por ***Leandro***, se realiza una sustitución masiva.    
* ***uv*** // Modo visual   
* ***gg*** // Copiar linear  
* ***p*** // Pega la línea copiada   
* ***2gg*** // Copia dos líneas       
* ***:r! ls /var/log*** // Me inserta en el archivo el resultado de ls  
* ***:r /var/log/auth.log*** // Me inserta el cotenido del arhivo ***auth.log*** desde el punto en el que se encuentra el cursos. ***Es importante recalcar que cuando se utiliza esta manera en Vim de abrir un fichero, el fichero original no presenta registro de accesos, ni modificaciones.*** Por temas de seguridad informática eso es delicado, ya que no tendrias registro de acceso al achivo.   


## Comando Tar y Unzip
Tar permite crear backups de forma controlada y automatizada. Los tipos de compresión mas utilizados son ***gzip, bzip2, xz***.
Mayor compresión, mayor tiempo y desgaste del procesador y disco duro. Zip no es recomendable para servidores, por no ser tan eficiente como xf. 

* ***tar -x*** // Para extraer
* ***tar -c*** // Para crear
* ***du -hsc * //*** Muestra el tamaño de los archivos    
* ***tar -cf carpeta.tar carpeta/*** // Create File carpeta.tar de la carpeta ***carpeta/***  
* ***tar -czf archivo.tar.zip carpeta/*** // Utilizar gzip para comprimir  
* ***tar -cJf archivo.tar.xz carpeta/*** // Utiliza xz para comprimir ***xz es el mayor factor de compresión***
* ***tar -xzf comprimido.tar.zip*** // Descomprime el archivo con el factor de descompresión ***z***  
* ***tar -tvf archivo.tar.zip***// Muestra el contenido del archivo comprimido, sin descomprimirlo, la ***v*** es de verbose    
* ***tar -xvf archivo.tar.zip carpetaSalida/archivo.mp3*** // Descomprime un solo archivo indicado con el nombre dentro del zip  
* ***tar -pc --backup -f Descargar.tar Descargas*** // Mantener los permisos y crear, ***pc***, va a hacer un backup con nombre de archivo  ***-f*** descargar.tar comprimiendo la carpeta Descargas/, esta manera matiene los permisos de los archivos  
* ***tar -pc --backup=t -f Descargar.tar Descargas*** // Mantener los permisos y crear, ***pc***, va a hacer un backup con nombre de archivo  ***-f*** descargar.tar comprimiendo la carpeta Descargas/, esta manera matiene los permisos de los archivos, con ***=t*** crea un número de backup    
* ***unzip archivo.zip*** // Descomprime un archivo.zip  

# Paquetes de software
Antes de proceder a la instalación de repositorios o de binarios, con ***yumy o rpm para centOS o RedHat, y dpkg, apt, aptitude, apt-get, para distribuciones basadas en Debian***, tenemos que aprender como realizar la instalación desde las fuentes. Para ello tenemos que descargar el paquete de la fuente de npm, para instalar software desde la fuente, en centOS es necesario tener la dependencia ***yum install make gcc*** o ***apt install make gcc***, para poder compilar en distribuciones basadas en Debian. 

* ***wget ftp://ftp.bitwizard.nl/mtr/mtr-0.92.tar.gz***  // Para descargar la fuente de repositorios  

Luego leer el archivo para ver los pasos ***nano README***, salir del archivo, y ejecutar ***./configure***  para  que se validen las dependencias. Luego hacer ***make***, si sale un error, entonces instalar ***yum install autoconf***, luego volver a compilar con ***make***, y despues instalar ***make install***, ahora ya esta instlado el comando, utilizar ***mtr 8.8.8***.

## Yum 

El gestor de paketes, en distribuciones basadas en RedHat, se llama ***rpm***, y algunos de sus gestores de command line interface, es ***yum***, es un gestor de paqueteria para realizar la instalación de sus correspondientes librerias. yum como tal posee múltiples herramientas de trabajo, es un gestor de aplicaciones muy organizado, el cual permite buscar, listar, instalar, desinstalar, limpiar, etc, todo el software en nuestra distribución.

Lo primero es comprobar si hay actualizaciones disponibles para nuestra distribución.

* ***yum check-update*** // Muestra paquetes listos para actualizar
* ***yum update*** // Actualiza todo el sistema
Para validar cuales paquetes estan listos para actualizar, 
* ***yum update nombrePaquete***  // Solo actualiza el paquete nombrado, y ninguno adicional   
* ***yum info nombrePaquete***  // Muestra información, arquitectura, versión, tamaño, y más sobre el repositorio nombrado   
* ***yum search nombreRepositorio***  // Busca todo lo relacionado al repositorio
* ***shitf+repag***  // Subir y bajar en la terminal para leer   
* ***yum search php | less***  // Procede a buscar de forma páginada la información, y detalla paquete por paquete    
* ***yum search php | grep mysql***  //  Todos los paquetes que tengan mysql dentro de su contenido
* ***yum list | less***  // Todos los paquetes disponibles para mi sistema   
* ***yum reinstall nombrePaquete***  // Reinstala un paquete, sirve por si tengo un paquete dañado, reconstruye la instalación
* ***yum remove nombrePaquete -y*** //  Borra el paquete nombrado, y acepta todos los mensajes  
* ***yum check***  // Valida los repositorios en línea, y los compara con los que estan en el cache del sistema   
* ***yum clean all***  // Eliminar caché y archivos innecesarios que ocupan lugar en el sistema   
* ***yum list install***  // Listado de paquetes para instalar en el sistema   
* ***yum list installed***  // Todos los repositorios instalados en el sistema   
* ***yum repo list***  // Muestra que repositorios estan instalados   
* ***yum repoinfo nombreRepositorio***  // Muestra información sobre el repositorio nombrado   
* ***yum provides /etc/ssh/sshd_config***  // Para saber a que paquetes le pertenece ese archivo de configuración     
* ***yum group***  // Los grupos son metapaquetes que cuando yo le indico que me lo instale, instala el paquete completo con sus dependencias   
* ***yum groups list***  //  Lista de grupos de repositorios disponibles para realizar una instalación
* ***yum group install "Web Server"***  // Me instala todos los paquetes del grupo "Web Server"   
* ***yum history***  // Las actividades que se han realizado   
* ***yum history info 3***  // Muestra el historial con mas información sobre los procedimientos realizados   
* ***yum install --downloadonly nombrePaquete***  // Solo descargará sin instalar  el paquete en la ruta cd /var/cache/yum/x86_64/7/epel(repositorio donde se descargo)/packages/archivo.rpm
* ***yum localinstall nombrePaquete***  // Instala el paquete que esta dentro de la carpeta ya descargado


## Rpm

Me permite ejecutar paquetes que ya hallan sido descargados:

* ***yum install --downloadonly sl***  // Descarga sin instalar ***sl***   
* ***rpm -ivh \ @.rpm***  // Me instala todos los paquetes -rpm v de verbose, i de install, h de que me instale de la forma de yum  
* ***rpm -info paquete***  // Obtener información del paquete  
* ***rpm -q -info paquete.rpm***  // Obtener información sobre si el paquete esta instalado   
* ***rpm -qa | grep sl***  // Buscar los paquetes instalados con ***sl***   
* ***rpm -Uvh nombrepPaquete.rpm***  // Actualiza un paquete   
* ***rpm -qf /etc/ssh/sshd_config***  //  Información sobre el paquete   ***sshd_config***, te indica a donde pertenece el paquete
* ***rom -qi paquete.rpm***  // Información sobre el paquete   
* ***rpm -i --test paquete.rpm***  // Testea el paquete para ver si hay algún error para instalarlo   



## Dpkg (Distribuciones basadas en Debian)
* ***apt update***  // Actualiza los repositorios, pero no se aplican las actualizaciones   
* ***apt upgrade***  // Aplica las actualizaciones al sistema de paquetes no escenciales, como firmwares o kernels 
* ***apt dist upgrade***  // Se aplican actualizaciones al kernel o sistemas escenciales del sistema   
* ***apt search htop***  // Buscar un paquete  
* ***apt-cache search htop***  // Buscar un paquete, con una salida mas agradable  
* ***apt install htop***  // Instala el paquete htop, y la salida es mas agradable que apt-get   
* ***apt autoremove***  //  Automaticamente desinstala todos los paquetes que se pueden eliminar sin problema  
* ***apt remove --purge htop***  //  Elimina el paquete htop junto a todos sus archivos de configuración que ocupan espacio  
* ***apt autoclean***  // Borra todos los paquetes de la cache para liberar espacio   
* ***apt install htop  sl-***  // Instala htop y elimina sl   
* ***apt remove htop sl+***  //  Borra htop e instala sl  
* *** ***  //   
* *** ***  //   
* *** ***  //   




* *** ***  //   
* *** ***  //   
* *** ***  //   

setup.noarch



* *** ***  //   
* *** ***  //   
* *** ***  //   
* *** ***  //   
* *** ***  //   

## Mis notas sobre comandos:

* ***uname -r***  // Que verison del Kernel tengo instalada 
* ***lsblk*** // Ver unidades de discos
* ***ifconfig*** // Dispositivos de red
* ***lspci*** // Ver dispositivos PCI
* ***man hier*** // Manual y Arquitectura: Sus descripciones
* ***cat /proc/uptime*** // Tiempo que estuvo encendido el equipo
* ***cat /proc/cpuinfo*** // Información sobre el procesador
* ***cat /proc/meminfo*** // Información sobre la memoria RAM
* ***file --help*** // Muestra cuales son las opciones que puedo enviar a ese comando
* ***man rm*** // Manual del comando rm, al presionar ***h*** indica mas ayuda, escribiendo ***/change***, nos busca palabras que coincidan en la descripción del comando.
* ***ls -l*** // Lista los archivos y muestra los permisos de cada uno
* ***ls -li*** // i de inodo
