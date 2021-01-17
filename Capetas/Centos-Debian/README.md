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
***
## Terminal y consola
La ***terminal*** se encarga de llamar a la ***consola***, la consola, es un interprete de comandos, y al mismo tiempo es un lenguaje de programación.

Un tipo de consola es la ***sh***, aunque en general también se utiliza ***bash***. La diferencia entre una consola y otra son los comandos y las variables que manejan. 

La ***consola***, también llamada ***cli o command line interface***, es aquella interface por línea de comandos que me permite interactuar con el sistema, y cada consola tiene sus funciones independientes, lo mismo con las diferentas terminales. 
***

## Man: Obtener ayuda e información sobre un comando SIN TENER ACCESO A INTERNET

Cuando no tenemos internet y necesitamos ayuda, en Linux los comandos tienen su propia ayuda, por ejemplo: 

***file --help***, automáticamente muestra ayuda sobre el comando, y las diferentes opciones que tiene el comando, quien lo escribe, la licencia, los bugs, ejemplos. Para cada comando exites su propio manual, este puede cambiar dependiendo de cada comando. 

***man info*** nos indica que para desplazarse entre la página manual de ayuda, utilizar los botones hacia arriba y hacia abajo, tambien hacia los lados. La letra ***q*** es para salir. 

Para buscar una palabra dentro del manual, se utiliza ***/palabra***, esto nos muestra cuales palabras coinciden dentro de la ayuda del comando, tocando ***n*** nos sigue muestra cuales palabras coinciden, y con ***N***, regresa a las que coinciden anteriormente.

***MAN(1)*** es un mensaje que nos indica en que nivel se esta buscando, los distintos niveles son para distintas funciones, el ***nivel 1***, hace referencia a los ejecutables y los comandos, el ***nivel 5***, hace refencia a los archivos.

***man -k passwd***, trae todos los comandos, referencias, o archivos, que tengan página manual sobre la palabras 
***passwd***.

***man -f passwd***, busca de forma exacta, es una manera también de obtener información de  que comando tengo que utilizar.

***man 5 passwd***, busca en el nivel 5, el archivo de configuración passwd.

***apropos pass***, es muy similar a lo que seria la opción ***k*** el manual.
****
## Apagar y reinciar el sistema
En Linux es recomendable reiniciar un servicio, y no reiniciar todo el servidor.

***init 0*** // Es el nivel mas bajo del sistema, "Apáguese", mata las conexiones y apaga bruscamente el sistema. Solo se recomienda en casos extremos.

***halt*** // Hasta que no termina los procesos no se apaga

***shutdown -h +60 "Esto se va a descontrolar"*** // Te da tiempo para cancelar el apagado del sistema, la ***h*** hace referencia a ***halt***.

***shutdown -c*** // Cancela el apagado

***poweroff*** 

Todos ejecutan ***init 0***, pero apagan adecuadamente el sistema.


***shutdown -r***// Reinicia el sistema
***reebot***
***init 6*** // Reinicia el sistema bruscamente

******

## System D
Unifica herramientas, y posee mejoras en el arranque del sistema, unifico las distribuciones en una misma herramienta.

No puede ser utilizado en otro sistema que no sea basado kernel de Linux, no es un estandar, por ejemplo en Unix, a diferencia de init, que es un demonio principal de gestión de arranque y de procesos en varios sistemas.

Tiene comandos útiles para, arranque del sistema, gestión de servicios, gestión del sistema, y gestión de registros.

****
## Utilizar alias
La definición de un alias es renombrar una línea de comandos, por otra, por ejemplo  ***el alias de Diego Armando Maradona, es d10s***.

***alias*** // Muestras los alias creados
***alias ls='ls color=auto'***// Crea un alias para ***ls***
***alias update='sudo apt-get update && sudo apt-get upgrade'*** // Crea un alias, pero si cierro la sesión el alias se borra

***nano .bashrc*** // Abre el editor nano el archivo bashrc del usuario, buscar en donde dice ***some more alias***, y escribir el alias sin ***#***, entonces no se va a perder luego de cerrar la sesión.

****
## Conocer el estado del sistema

***lshw*** // obtiene información desde el sistema  ***dmidecode***// obitene información directamente desde la bios
***lshw*** // Información del sistema    
***dmidecode*** // Información del sistema    
***lshw -C cput*** // Información sobre el CPU  
***lshw -C memory*** // Información sobre la memoria RAM  
***dmidecode | head -50*** // Las primeras 50 líneas  
***free*** // Cuanta memoria RAM en bytes tengo  
***free -h*** // Cuanta memoria RAM en Gb tengo  
***lspci*** // Lista los dispositivos PCI buses hay disponibles en el sistema 
***id*** // Muestra en que grupo y usuario pertenesco  
***group*** // A que grupo pertenezco  
***w*** // Muestra quienes estan conectados  
***who*** // Muestra a que hora se conecto cada usuario   
***uptime*** // Muestra hace cuanto fue encendido el sistema  
***whoami***  // Quien soy yo   
***top***  // Gestor de procesos  
***last***  // Últimas conexiones satisfactorias en el sistema  
***lastb***  // Últimas conexiones rechazadas (SE RECOMIENDA SEMANALMENTE PARA EVIDENCIAR ATAQUES)  
***vmstat***  // Uso de memoria en tanto a los buffers  
***ip addr***  // Muestra los adaptadores de red del sistema  
***ip route***  //  Muestra las rutas del sistema 
***route -e***  //  Muestra las rutas del sistema 
***ip link***  // El estado de un enlace
***netstat -n*** // Conexiones en el momento  
***netstat -nt*** // Conexiones en el momento con protocolo tcp  
***netstat -nu*** // Conexiones en el momento con protocolo udp  
***ss*** // Muestra las conexiones, pero mas enfocado a sockets, informa que tipos de conexiones estoy utilizando, por ejemplo http, https  
***dmesq*** // Da toda la información correspondiente a los dipositivos de arranque, red, disc duro, librerias, etc. Log de arranque del sistema, solo guarda el último inicio del kernel.      
***ps*** // Información de los procesos utilizados por el usuario 
***ps -aux*** // Es lo mismo que el top, pero muestra todos los procesos que estan ejecutandose  
***pstree*** // Más detallado, procesos en arquitectura de árbol 
***df -h*** // Muestra el tamaño del disco duro  
***lsblk*** //  Muestra el tamaño del disco duro en forma de árbol
******   
## Comando find  
Es mas poderoso que un buscador gráfico, nos permite buscar por fechas, modificaciones, accesos, múltiples características de un archivo, es muy complejo y completo.

***find . -name a.@*** // Que busque donde estoy parado y coincidan con el nombre exacto y con cualquier extensión, @ es *.  
***find -name [Aa].@*** //   
***find -name [Aa][A-Z].@*** //   
***find . -iname A.@*** //  Que busque donde estoy parado y el nombre sea inexacto, y con cualquier extensión, @ es *.   
***find /home/soporte --type d*** // Busca en soporte los archivos de tipo directorio  
***find /home/soporte --type d | grep Descargas*** //  Solamente me busque directorios en Descargas  
***find /home/soporte --type d -name D@*** // Solamente me busque directorios que comiencen exactamente con D  
***find /home/Descargas -type f -size +1M*** // Que me busque en descargas todo del tipo archivo que pesen mas de 1 Mb   
***find /home/Descargas -type f -size +1M -exec ls -lah {} \;*** //  Que me busque en descargas todo del tipo archivo que pesen mas de 1 Mb, y me ejecute ls -lah
***find /home/Descargas -type f -size +1M -exec du -hs {} \;*** //  Que me busque en descargas todo del tipo archivo que pesen mas de 1 Mb, y me ejecute du -hs
***find . -inum 4457184*** // Busca un archivo por su inodo, es bueno cuando el nombre tiene algún caracter especial.  
***find . -inum 4457184 -exec rm -rf {}\;*** // Busca y borra el archivo conflictivo por su inodo  
***find /home/soporte/ -mtime -5*** // Buscar archivos modificados hace menos de 5 días. 
*** *** //  
*** *** //  





*** *** //  



****
****




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
* *** *** //
* *** *** //
