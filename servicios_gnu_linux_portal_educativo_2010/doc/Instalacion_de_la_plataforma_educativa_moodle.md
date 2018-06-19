# 3.- Instalación de la plataforma educativa moodle
<div style="text-align: justify;">'<i><b>Moodle'</b></i> es un <a href="http://es.wikipedia.org/wiki/Ambiente_Educativo_Virtual" title="Ambiente Educativo Virtual">Ambiente Educativo Virtual</a>, sistema de gestión de cursos, de <a href="http://es.wikipedia.org/wiki/Software_libre" title="Software libre">distribución libre</a>, que ayuda a los educadores a crear comunidades de aprendizaje en línea. Este tipo de plataformas tecnológicas también se conoce como <a href="http://es.wikipedia.org/wiki/LMS_%28Learning_Management_System%29" title="LMS (Learning Management System)">LMS (Learning Management System)</a>.<br /><br />La página oficial de moodle es <a href="http://moodle.org/">http://moodle.org/</a><br /><br />La última versión de moodle es la 1.9.7, y la página de descarga es: <a href="http://download.moodle.org">http://download.moodle.org/</a> Podemos bajar el págute comprimido en zip o en tar.gz desde la página o podemos utilizar el comando wget.<br /><br />1) Nos situamos en nuestro servidor avatar en el directorio /var/www y ejecutamos la siguiente instrucción:<br /><pre>avatar:/var/www# wget http://download.moodle.org/stable19/moodle-1.9.7.tgz</pre>A continuación descomprimimos el fichero comprimido:<br /><pre>avatar:/var/www# tar xzvf moodle-1.9.7.tgz</pre>Ya podemos borrar el fichero comprimido. Además ahora es la hora de elegir el nombre del directorio donde vamos a tener nuestra plataforma, una sugerencia es renombrar la carpeta moodle a plataforma, de esta forma para acceder al moodle desde el ciente tenderemos que acceder a http://avatar/plataforma:<br /><pre>avatar:/var/www# rm moodle-1.9.7.tgz
avatar:/var/www# mv moodle plataforma</pre>2) Antes de comenzar la instalación vamos a crear una base de datos y un usuario en el servidor mysql que será el propietario de la base de datos anteriormente creada. Para ello accedemos al servidor mysql, se nos pedirá una contraseña que es la del root que indicamos durante su instlación.<br /><pre>avatar:/var/www# mysql -u root -p
 &gt; CREATE DATABASE moodle <font color="red" style="color: rgb(0, 0, 0);">DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci</font><span style="color: rgb(0, 0, 0);">;
 </span>&gt; GRANT SELECT,INSERT,UPDATE,DELETE,CREATE,DROP,INDEX,ALTER ON moodle.* TO moodleuser@localhost IDENTIFIED BY 'yourpassword';
 &gt; quit
avatar:/var/www# mysqladmin -p reload </pre>El último comando recarga los permisos de los usuarios. En el ejemplo anterior hemos creado la base de datos moodle y un usuario llamado moodleuser con la contraseña yourpassword (que obviamente deberás cambiar).<br /><br />3) Para comenzar la instalación lo único que tenemos que hacer es acceder a la web desde el cliente a la dirección http://avatar/plataforma<br /><br />* En primer lugar elegimos el idioma<br /><br /><img border="0" vspace="0" hspace="0" title="1" alt="1" src="img/moodle$@SLASH@$moodle1.png" /><br /><br />* A continuación se hace una comprobación de los ajuste de PHP. Seguramente te faltará algún paquete, averigua cual e instálalo y si no es así utiliza el foro para comentar que puntos no se cumplen.<br /><br /><img border="0" vspace="0" hspace="0" title="2" alt="2" src="img/moodle$@SLASH@$moodle2.png" /><br /><br />* En la siguiente pantalla tenemos que indicar dos datos importantes:<br />
  <ul>
    <li><span style="font-weight: bold;">Dirección Web</span>: Especifique la dirección web completa en la que se accederá a Moodle.</li>
    <li><span style="font-weight: bold;">Directorio de Datos:</span> Es necesario un lugar donde Moodle pueda guardar los archivos subidos. Este directorio debe ser leíble Y ESCRIBIBLE por el usuario del servidor web, pero este lugar no debe ser accesible directamente a través de la web.</li>
  </ul><img border="0" width="1278" vspace="0" hspace="0" height="598" title="3" alt="3" src="img/moodle$@SLASH@$moodle3.png" /><br /><br />Los datos que nos ponen por defecto son adecuados, pero debemos crear el directorio moodledata, darles permisos de lectura y escritura para el usuario del servidor web www-data:<br /><pre>avatar:/# mkdir /var/moodledata
avatar:/# chown www-data:www-data /var/moodledata
avatar:/# chmod 777 -R /var/moodledata</pre>* En la siguiente pantalla indicamos los datos de la base de datos:<br />
  <ul>
    <li><b>Tipo:</b> MySQL</li>
    <li><b>Servidor:</b> en nuestro caso localhost<br /></li>
    <li><b>Nombre:</b> nombre de la base de datos, en nuestro caso moodle<br /></li>
    <li><b>Usuario:</b> usuario de la base de datos</li>
    <li><b>Contraseña:</b> contraseña de la base de datos</li>
    <li><b>Prefijo de tablas:</b> prefijo a usar en los nombres de las tablas (opcional)</li>
  </ul><img border="0" width="1276" vspace="0" hspace="0" height="726" src="img/moodle$@SLASH@$moodle4.png" alt="4" title="4" /><br /><br />* A continuación se hace una comprobación del servidor: se nos pide que instalemos algunas extensiones de PHP, pero ninguna son obligatorias. Continuamos adelante.<br /><br /><img border="0" width="1276" vspace="0" hspace="0" height="701" title="5" alt="5" src="img/moodle$@SLASH@$moodle5.png" /><br /><br />* A continuación descargamos el paquete de idioma español. Pulsamos el botón de Descarga.<br /><br /><img border="0" width="1272" vspace="0" hspace="0" height="437" title="6" alt="6" src="img/moodle$@SLASH@$moodle6.png" /><br /><br />* Estamos terminando: Ya tenemos toda la configuración preparada, en la siguiente pantalla nos aparece el contenido del fichero de configuración. Copiamos el contenido y lo pegamos en el fichero /var/www/plataforma/config.php (este fichero lo tienes que crear).<br /><br /><img border="0" width="1278" vspace="0" hspace="0" height="708" title="7" alt="7" src="img/moodle$@SLASH@$moodle7.png" /><br /><br />* Se va a comenzar la instalación propiamente dicha. Donde se van a ir creando las tablas necesarias en la base de datos. Puede elegir la opción <span style="font-style: italic;">Unattended operation</span> y no será necesario que hagas nada más hasta la siguiente pantalla.<br /><br />* Configuración de la cuenta del administrador: Debes indicar nombre de usuario administrador, contraseña, nombre y apellido, correo electrónico, provincia y país.<br /><br /><img border="0" width="1269" vspace="0" hspace="0" height="752" title="8" alt="8" src="img/moodle$@SLASH@$moodle8.png" /><br /><br />* Configuración del sitio: Debes indicar el nombre de la página, el nombre corto y una descripción.<br /><br /><img border="0" width="1280" vspace="0" hspace="0" height="949" title="9" alt="9" src="img/moodle$@SLASH@$moodle9.png" /><br /><br />* Y hemos terminado la instalación, puedes encontrar manuales sobre moodle en los siguientes enlaces:<br />
  <ul>
    <li> <a href="http://www.josedomingo.org/web/course/view.php?id=9">Moodle para Profesores</a></li>
    <li><a href="http://www.josedomingo.org/web/course/view.php?id=8">Moodle para Estudiantes</a></li>
    <li><a href="http://www.josedomingo.org/web/course/view.php?id=10">Características de Moodle</a></li>
  </ul></div>