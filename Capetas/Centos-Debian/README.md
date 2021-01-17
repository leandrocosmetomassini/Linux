![](https://webtematica.com/sites/default/files/styles/790px/public/blog-img/servidores-web.jpg?itok=PXBE6Ehg&timestamp=1452631683)  


# Pasos importantes para tener siempre en cuenta:

 Verficiar si el hardware, (En especial la tarjeta gráfica), es compatible con cada distribución, y saber si los drivers fueron desarrollados con software libre, código abierto. Ubuntu y CentOS tienen drivers de software privativo. Si es compatible en RedHat, también es compatible en CentOS.
    


  * [Centos Hardware List](https://wiki.centos.org/es/AdditionalResources/HardwareList)

  * [Ubuntu server certificacion](https://certification.ubuntu.com/server)



   * [Debian releases](https://www.debian.org/releases/etch/i386/ch02s01.html.en)


   * [Debian unofficial con algunos drivers con código privativo](https://cdimage.debian.org/cdimage/unofficial/non-free/firmware/)

    Por seguridad no es recomendable instalar aplicaciones que no formen parte de un repositorio o de la tienda oficial, en caso de que un programa externo ocacione problemas, no sera parte de la garantia.


A la hora de instalar, se recomienda hacer las particiones manualmente, y tener en cuenta cual es conveniente utilizar, y que tamaños darles. Por ejemplo si es para un servidor web, se recomienda que la partición mas grande sea la de ***/var***.

Cuando el instalador pregunte si deseas configurar el gestor de paquetes, lo recomendable es elegir Estados Unidos, ya que  que en otros paises tardan mucho en actualizarse.

Tener en cuenta con el ***administrador de las IP***, que ip esta libre para nuestro equipo. También tener en cuenta que si compartimos datos con la comunidad de Debian en un ambiente de producción, estariamos gastando ancho de banda.

## Terminal y consola
La ***terminal*** se encarga de llamar a la ***consola***, la consola, es un interprete de comandos, y al mismo tiempo es un lenguaje de programación.

Un tipo de consola es la ***sh***, aunque en general también se utiliza ***bash***. La diferencia entre una consola y otra son los comandos y las variables que manejan. 

La ***consola***, también llamada ***cli o command line interface***, es aquella interface por línea de comandos que me permite interactuar con el sistema, y cada consola tiene sus funciones independientes, lo mismo con las diferentas terminales. 














## Mis notas sobre comandos:

* ***uname -r***  // Que verison del Kernel tengo instalada 
* ***lsblk*** // Ver unidades de discos
* ***ifconfig*** // Dispositivos de red
* ***lspci*** // Ver dispositivos PCI
* ***man hier*** // Manual y Arquitectura: Sus descripciones
* ***cat /proc/uptime*** // Tiempo que estuvo encendido el equipo
* ***cat /proc/cpuinfo*** // Información sobre el procesador
* ***cat /proc/meminfo*** // Información sobre la memoria RAM
* *** *** //
* *** *** //
* *** *** //
* *** *** //
* *** *** //
* *** *** //
