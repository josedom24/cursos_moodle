# Trabajando con paquetes. Instalando servicios
<div style="text-align: justify;"> Cuando usamos APT para instalar paquetes hace dos tareas por separado: en un primer paso descarga de los repositorios los paquetes que va a instalar, para a continuación usar la instrucción dpkg para desempaquetar y configurar cada paquete. Veamos algunas cuestiones relacionadas con estas dos tares.<br /><br /> </div>
<h2 style="text-align: justify;">Descarga de los paquetes para su instalación</h2>
<div style="text-align: justify;"><br />Todos los paquetes descargados por APT se almacenan en un directorio, para posteriormente poder instalarlo con dpkg. El directorio donde podemos encontrar los paquetes bajados es:<br /><br /><pre>/var/cache/apt/archives</pre><br />Para borrar esta cache de paquetes podemos usar la opción siguiente de APT:<br /><br /><pre># apt-get clean</pre><br /> </div>
<table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />1) Comprueba los paquetes deb que tienes en tu cache de paquetes.<br /><br />2) ¿Qué ocurre si desinstala un paquete y lo vuelves a instalar, si el paquete está en la cache?<br /><br />3) Borra la cache de paquetes y comprueba que se han borrado. Te en cuenta que a continuación deberás instalar algún paquete para tener paquetes en la cache y seguir haciendo las tareas.<br /><br />
    </td>
  </tr></tbody>
</table>
<div style="text-align: justify;"><br /> </div>
<h2 style="text-align: justify;">dpkg: Trabajando con paquetes .deb</h2>
<div style="text-align: justify;">Recordamos algunas opciones de dpkg:<br /><br />Para instalr un paquete deb usamos:<br /><pre># dpkg -i nombredelpaquete.deb</pre><br />Para eliminar el paquete instalado, debemos poner:<br /><pre># dpkg -r nombredelpaquete</pre>Tambien podemos usar para eliminar un paquete el parámetro --purge(-P)<br /><pre># dpkg -P nombredelpaquete</pre>Con esto borramos la aplicación y los archivos de configuración.<br /><br />Ahora si solo queremos ver el contenido del paquete deb podemos poner<br /><pre># dpkg -c nombredelpaquete.deb</pre><br />Para obtener información acerca del paquete tal como el nombre del autor, el año en que fue compilado y una descripción corta de su uso podemos poner<br /><pre># dpkg -I nombredelpaquete.deb</pre><br />Para conocer si tenemos instalado un determinado paquete podemos poner<br /><pre># dpkg -s nombredelpaquete</pre><br />Si nosotros queremos conocer que archivos nos instala una determinada aplicación podemos poner<br /><pre># dpkg -L nombredelpaquete </pre>Si queremos saber a qué paquete pertenece un fichero, podemos poner:<br /><pre># dpkg -S nombredefichero</pre> </div>
<table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />1) Escoge un paquete que tengas en la cache, elimínalo con dpkg y a continuación vuelve a instalarlo.<br /><br />2) Escoge un paquete que tengas en cache y visualiza su contenido y la información de dicho paquete.<br /><br />3) Vamos a identificar los ficheros instalados en el sistema de un paquete &quot;servicio&quot;, para ello vamos a instala con apt-get el servidor de correo &quot;postfix&quot; y a continuación usando la opción -L de dpkg identifica los ficheros y directorios instalando usando como guía el siguiente <a href="$@PAGEVIEWBYID*986@$">documento</a>.<br /><br />4) Comprueba en qué paquete del sistema está el fichero /etc/dhcp3/dhclient.conf<br /><br />
    </td>
  </tr></tbody>
</table>
<div style="text-align: justify;"> <br /> </div>
<h2 style="text-align: justify;">dpkg-reconfigure: Reconfigurando los paquetes instalados</h2>
<div style="text-align: justify;"><br />Cuando instalamos un paquete con APT, se descarga, se descomprime y por último se configura. Si queremos configurar de nuevo un paquete ya instalado usamos la instrucción dpkg-reconfigure.<br /><br />Con la opción -p podemos indicar el nivel de detalle que se hará la configuración: low (bajo) o high (alto).<br /><br /> </div>
<table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />1) Reconfigura el paquete debconf, que se encarga precisamente de la configuración de los paquetes debian.<br /><pre>dpkg-reconfigure debconf</pre>
    </td>
  </tr></tbody>
</table>
<div style="text-align: justify;"><br /></div>
