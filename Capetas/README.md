# Mis notas de comandos frecuentes

### Hardware

###### Ficheros dentro de proc

*  [Documentacion de Linux sobre el directorio /proc](http://tldp.org/LDP/Linux-Filesystem-Hierarchy/html/proc.html)    

cat /proc/cpuinfo // Muestra informacion sobre la cpu  
cat /proc/meninfo // Uso de memoria en el sistema  
cat /proc/partitions // Particiones del sistema  
cat /proc/interrupts // Tabla de interrupciones en el sistema   
cat /proc/ioports // Ubicacion de los diversos dispositivos en el banco de memoria  
cat /proc/dma // Direcciones de acceso directo a memoria  

###### Dispositivos PCI

  Hay dos tipos de dispositivos en el sistema,  “cold plug” y  “hot plug”, la diferencia es la forma en la que pueden ser conectados y desconectados en el sistema, “cold plug”, cuando el dipositivo esta apagado, por ejemplo CPU, memoria RAM, disco duro, en cambio “hot plug”, se pueden desconectar y conectar con el sistema operativo en funcionamiento.  

lspci // Listado de los dispositivos PCI del sistema
man lspci // Manual del comando lspci
lspci -t // Lista en arbol de buses PCI
lspci -nn // Nombre del fabricante y dispositivo con codigo numero del dispositivo PCI
setpci // Permite configurar el dispositivo, (Es necesario conocer a bajo nivel el hardware que estamos consultando)

###### Modulos del Kernel

  En un sistema Linux los modulos del Kernel representan lo que seria los controladores o drivers del hardware que tenemos en el sistema. En /lib/modules Linux almacena los drivers de los diversos elementos Hardware que tenemos en el sistema.  
  
  lsmod // Muestra los modulos cargados actualmente en la memoria RAM
  cd /lib/modules/4.19.0-8-amd64/ // Serie de ficheros que dan informacion de los modulos
  netlink_diag.ko // Ficheros .ko son drivers en Linux, por estandar se guardan en /lib/modules
  modinfo nombreModulo // Ofrece informacion a nivel detallado del modulo, por ejemplo donde esta ubicado ese driver
  insmod // Para cargar un modulo en el sistema con el fichero.ko dentro de /lib/modules/
  
  

