# 2.- Instalación de un servidor LAMP (Linux, Apache, MySQL y PHP)
<div class="box generalbox generalboxcontent boxaligncenter clearfix">
  <div style="text-align: justify;">Ahora vamos a instalar los paquetes necesarios para tener un entorno LAMP.<br /><br />Apache:<br /><pre>avatar:~# apt-get install apache2</pre>MySQL:<br /><pre>avatar:~# apt-get install mysql-common mysql-client mysql-server
</pre>Durante la instalación del servicio se nos pedirá la contraseña del usuario root del servidor mysql.<br /><br />PHP5:<br /><pre>avatar:~# apt-get install php5 libapache2-mod-php5 php5-mysql</pre>Eso es todo, como gestor de la base de datos podemos utilizar phpmyadmin, que es una aplicación php que me permite acceder a todas las funciones de MySQL<br /><pre>avatar:~# apt-get install phpmyadmin
</pre>
    <p>En la instalación del paquete phpmyadmin nos preguntará el servidor web que estamos utilizando, para realizar la configuración automática. En nuestro caso escogeremos la opción Apache2.<br /></p>
    <p>Voila!, eso es todo.<br /></p></div><hr style="margin-left: 0px; margin-right: 0px;" />
  <div style="text-align: justify;"> </div>
  <p style="text-align: justify;">Para probar el funcionamiento de Apache y PHP es habitual crear un documento crear un documento index.php en el directorio /var/www con el siguiente contenido (hay que borrar el archivo index.html que hay en /var/www para que no sea el que se visualice por defecto):<br /></p>
  <div style="text-align: justify;"> </div> <pre style="text-align: justify;"><font face="courier new,courier,monospace">&lt;html&gt;
&lt;body&gt;
 &lt;? echo phpinfo(); ?&gt;
&lt;/body&gt;
</font><font face="courier new,courier,monospace">&lt;/html&gt;
</font></pre>
  <div style="text-align: justify;"> </div>
  <div style="text-align: justify;"> </div>
  <p style="text-align: justify;"><font face="Trebuchet MS,Verdana,Arial,Helvetica,sans-serif">Para acceder desde el navegador del cliente al servidor web vamos a utilizar el nombre del servidor (avatar) para ello hay que indicar en el fichero /etc/hosts la relación que hay entre su nombre y su dirección IP.</font></p>
  <div style="text-align: justify;"><pre># nano /etc/hosts

192.168.2.1 avatar </pre></div>
  <p style="text-align: justify;"><font face="Trebuchet MS,Verdana,Arial,Helvetica,sans-serif">De esta manera, cuando en en navegador del cliente pongamos </font><font face="Trebuchet MS,Verdana,Arial,Helvetica,sans-serif">http://avatar</font><font face="Trebuchet MS,Verdana,Arial,Helvetica,sans-serif">, debe aparecer información sobre la versión PHP instalada.</font></p>
  <p style="text-align: justify;"><font face="Trebuchet MS,Verdana,Arial,Helvetica,sans-serif"><img border="0" width="1280" vspace="0" hspace="0" height="949" title="phpinfo" alt="phpinfo" src="img/phpinfo.png" /></font></p>
  <p style="text-align: justify;"><font face="Trebuchet MS,Verdana,Arial,Helvetica,sans-serif">Y si queremos acceder al gestor de la base de datos debemos acceder a http://avatar/phpmyadmin</font></p>
  <p style="text-align: justify;"><img border="0" width="1280" vspace="0" hspace="0" height="949" title="phpmyadmin" alt="phpmyadmin" src="img/phpmyadmin.png" /><br /></p>
  <p style="text-align: justify;"><font face="Trebuchet MS,Verdana,Arial,Helvetica,sans-serif"><br /></font></p></div>
