# Instalación de Apache+PHP+MySQL
<div style="text-align: justify;"> Instalando Apache:<br /><br /><span style="font-weight: bold;">#apt-get install apache2</span><br style="font-weight: bold;" /><br />Instalando MySQL:<br /><br /><span style="font-weight: bold;">#apt-get install mysql-common mysql-client mysql-server</span><br /><br />Instalando Php 5.0:<br /><br /><span style="font-weight: bold;">#apt-get install php5 libapache-mod-php5 php5-mysql</span><br /><br /><br />Eso es todo, como gestor de la base de datos podemos utilizar phpmyadmin, programa php que me permite acceder a todas las funciones de mySql<br /><br /><span style="font-weight: bold;">#apt-get install phpmyadmin.</span><br /></div><hr style="margin-left: 0px; margin-right: 0px;" />
<div style="text-align: justify;"> </div>
<p style="text-align: justify;">Para probar el funcionamiento de apache y PHP, crea un documento index.php y copialo en la carpeta /var/www</p>
<div style="text-align: justify;"> </div>
<p style="text-align: justify;"><font face="courier new,courier,monospace">&lt;html&gt;<br />&lt;body&gt;<br /> &lt;? echo phpinfo(); ?&gt;<br />&lt;/body&gt;<br /></font><font face="courier new,courier,monospace">&lt;/html&gt;</font></p>
<div style="text-align: justify;"> </div>
<p style="text-align: justify;"><font face="courier new,courier,monospace"> </font><br /></p>
<div style="text-align: justify;"> </div>
<p style="text-align: justify;"><font face="Trebuchet MS,Verdana,Arial,Helvetica,sans-serif">Cuando en un navegador pongamos </font><a href="http://localhost/"><font face="Trebuchet MS,Verdana,Arial,Helvetica,sans-serif">http://localhost</font></a><font face="Trebuchet MS,Verdana,Arial,Helvetica,sans-serif">, debe aparecer información sobre la versión PHP instalada.</font></p>
