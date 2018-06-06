# Ejercicio: Planificación y realización de copias de seguridad del servidor
<div class="box generalbox generalboxcontent boxaligncenter clearfix">
  <div style="text-align: justify;">
    <h1><font size="5">Realización de script para realizar la copia de seguridad del servidor</font></h1><font size="3"><br />En este ejercicio vamos a realizar un script en bash para realizar las copias de seguridad de nuestro servidor avatar, que cumpla las siguientes especificaciones:<br /><br /></font>
    <ol>
      <li><font size="3">Realiza el proceso de forma completamente automático: Para ello vamos a hacer que el script de copia de seguridad se ejecute en el cron diariamente.<br /><br /></font></li>
      <li><font size="3">Decidir qué información es necesaria guardar: Con los servicios que hemos ido instalando durante este curso, hemos decidio hacer copia de seguridad de los siguientes directorios: <br /><span style="font-weight: bold;">/etc /home /root /var/cache/bind /var/log /var/lib /usr/local /var/www,</span><br /> además vamos a hacer una copia de seguridad de la lista de paquetes actualmente instalado en el sistema. La lista de directorios la podemos guardar en una variable $DIRS.<br /><br /></font></li>
      <li><font size="3"> Utilizar la herramienta tar: La sintaxis que se ha usado para el comando tar es:<br /></font>
        <ul>
          <li><font size="3">Completa: tar czf $FICHERO_TGZ $DIRS</font></li>
          <li><font size="3">Incremental: tar czf $FICHERO_TGZ $DIRS -N $FECHA_AYER</font></li>
        </ul></li><font size="3"> La variable $FICHERO_TGZ contiene el nombre de la copia de seguridad y la variable $FECHA_AYER. Una copia de seguridad incremental sólo guarda los archivos que se han modificado desde la fecha indicada. <br /><br /></font>
      <li><font size="3">Incluir la fecha de realización en el nombre del fichero de copia: El nombre del fichero donde guardamos la copia de seguridad será de la forma backup_fecha.tar.gz, para poner la fecha en el nombre del fichero utilizaremos el comando bash date +%F<br /><br /></font></li>
      <li><font size="3">Almacenar la copia de seguridad en el directorio local /backup<br /><br /></font></li>
      <li><font size="3">Transferir la copia de seguridad en otro dispositivo de almacenamiento: Para mayor seguridad lo lógico es guardar la copia de seguridad que vamos a realizar en otro dispositivo de almacenamiento, por ejemplo en otro servidor de nuestra red, en un dispositivo NAS, etc., pero con nuestro esquema de trabajo lo más fácil es usar a nuestro ordenador cliente para guardar la copia. Para ello, vamos a utilizar ssh usuando claves públicas para la autentificación y usando el comando scp para hacer la copia.</font></li><font size="3"><br /></font>
      <li><font size="3">Semanalmente realizar una copia completa: Para llevar a cabo esta acción, podemos controlar qué día es cuando se ejecuta el script. Así, con sentencias de control (if) realizaremos un tipo de copia u otra. Para averiguar si es domingo o cualquier otro día he usado: date +%w. El comando anterior devuelve '0' en caso de ser domingo. En caso contrario devuelve números del 1 al 6 (de lunes de sábado respectivamente).<br /><br /></font></li>
      <li><font size="3">Diariamente realizar una copia incremental: La ventaja principal de usar la copia incremental es el poco tamaño que ocupa cada copia incremental (depende de cuántos ficheros se modifiquen). La desventaja principal es que deben existir todas las copias incrementales previas a la del último día para mantener todos los datos cuando haya que restaurarla. En este caso se hará una copia incremental cada día tomando como intervalo de modificación de un fichero el día anterior. Es decir, en cada copia se guardarán los ficheros que hayan sido modificados desde el día anterior (manteniendo su estructura en el sistema de directorios). La sintaxis para realizar la copia la hemos indicado anteriormente, pero para poder obtener el día anterior de la fecha actual se ha usado el siguiente comando: date -d yesterday +%F<br /><br />Al realizar copias incrementales, no se puede permitir que no exista la copia de un día. Para ello se ha creado un fichero de control llamado 'lastcopy' que tendrá en cuenta cuándo fue el último día que se realizó una copia. Así, la copia incremental se realizará desde dicho día.</font></li>
    </ol><font size="3"><br />Algunas observaciones a tener en cuenta:<br /><br /></font>
    <ol>
      <li><font size="3">Toda la información que devuelva un proceso, ejecutado en el cron, por la salida estándar será enviada por correo. Por lo tanto todos los mensajes que escribamos en la salida estandar con el comando echo se mandarán por correo.<br /><br /></font></li>
      <li><font size="3">Se debe realizar el script sabiendo que en el cleinte existe un directorio donde se van a almacenar las copias de seguridad generadas en el servidor. El nombre de ese directorio se guardará en la variable $DIR_REM<br /><br /></font></li>
      <li><font size="3">Se deben realizar comprobaciones sobre la existencia de los directorios y los ficheros necesarios para el funcionamiento del script:</font></li>
    </ol>
    <ul style="margin-left: 40px;">
      <li><font size="3"> Crear el directorio /backup si no existe.</font></li>
      <li><font size="3"> Si no existe el fichero /backup/lastcopy se creará con el valor de ayer (date -d yesterday +%F)</font></li>
    </ul><font size="3"><br />Esquema del script copia de seguridad:<br /><br /><span style="font-weight: bold;">backup.sh</span><br /><br /></font><pre><font size="3">#!/bin/bash
##Definiendo las constantes
DIR_BACKUP='/backup'
DIR_REM='copia'
HOST='cliente.example.com'
DIRS='etc home root usr/local var/cache/bind var/lib var/log var/www'
DIR_TMP='/media/backup'
FECHA=`date +%F`
FECHA_AYER=`date -d yesterday +%F`
##Creando el directorio de backup en caso de no existir
...
##Comprobamos si existe un fichero en /backup llamado 'lastcopy'
##Su utilidad será la de registrar la última copia que se realizó.
##En caso de no existir se pone la fecha de ayer
...
##Realizando la acción dependiendo del día
##El 0 representa el domingo en el formato date +%w
## Si el día actual es domingo realizamos copia completa
...
##sino realizamos copia incremental
....</font></pre></div></div>
