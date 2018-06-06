# Virtual Hosting: Creación y gestión de dos subdominios
<div style="text-align: justify;">El objetivo de esta práctica es la construcción de un sitio web que se pueda asemejar a las necesidades de un centro educativo. En las prácticas posteriores iremos mejorando la solución.<br /><br /><span style="font-weight: bold;">Definición del problema</span><br /><br /> Suponemos que el centro educativo ha comprado el siguiente dominio: <span style="font-weight: bold;">ies.org</span>.<br /><br />Nosotros vamos a crear dos subdominios (<span style="font-weight: bold;">www.ies.org</span> y <span style="font-weight: bold;">informatica.ies.org</span>) que van a ser gestionado por un servidor web Apache2 usando dominios virtuales.<br /><br />En el primer subdominio (www.ies.org) vamos a tener la página del centro donde en una práctica posterior instalaremos un CMS.<br /><br />El segundo subdominio (informatica.ies.org) es donde vamos a alojar la página del departamento de informática y donde los profesores del departamento van a tener sus páginas personales.<br /><br />Además de esto vamos a tener un servidor ftp (<span style="font-weight: bold;">ftp.ies.org</span>) que nos permita el mantenimiento de las distintas páginas desde el exterior.<br /><br />Queremos conseguir la siguiente funcionalidad:<br /><br />
  <ol>
    <li>La página alojada en el dominio www.ies.org sólo la podrán gestionar lel usuario <span style="font-weight: bold;">admin</span>.</li>
    <li>La página alojada en el dominio informatica.ies.org sólo la podrán gestionar los usuarios que pertenezcan al grupo <span style="font-weight: bold;">profesor</span>.</li>
    <li>Los profesores o alumnos del departamento tendrá un directorio público html_public en su home donde se alojarán sus páginas personales, que se podrán acceder a ellas en la dirección informatica.ies.org/~usuario (Esto se realizará usando el módulo userdir.mod que veremos en una práctica posterior).</li>
    <li>En otra práctica implementaremos que cada página ofrezca sus estadísticas usando awstats.<br /></li>
    <li>En la última práctica veremos como construir el sistema usando usuario s virtuales guardadores en un directorio LDAP.<br /></li>
  </ol><br /><span style="font-weight: bold;">Paso previo</span><br />
  <ul>
    <li>Si estamos en un caso real, en el servidor DNS de nuestro proveedor de internet crearemos los tres subdominios apuntando a nuestra IP pública. En nuestro router tendremos redirigido el puerto 80 al oredenador que haga la función de servidor Web. Del mismo modo el router tendrá redirigidos los puertos 20 y 21 al ordenador que funcione como servidor ftp (ftp.ies.org).<br /></li>
    <li>En nuestro caso vamos a usar estos nombres de dominios en nuestra red local (mortadelo será el servidor web y ftp, y filemón o nuestra maquina real (Ubuntu) la utilizaremos como cliente. Tenemos dos posibilidades: si tenemos el servidor DNS funcionando crearemos los tres nombres de subdominios apuntando a mortadelo, o tendremos que indicar esa relación en el fichero /etc/hosts de los ordenadores donde vamos a probar el servidor.</li><br />
  </ul><span style="font-weight: bold;">1) Creación de los usuarios y grupos<br /><br /><span style="font-weight: bold;"></span></span>
  <table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
    <tr>
      <td width="100%" valign="top"><br />
        <div style="text-align: justify;">1) Crea el usuario <span>admin</span>, que gestionará la página www.ies.org<br />2) Crea el grupo <span style="font-weight: bold;">profesores</span><br />3) Crea dos usuarios:<br /></div>
        <ul style="text-align: justify;">
          <li>Felisa: que va a ser profesora del departamento y va a tener como grupo principal <span style="font-weight: bold;">profesores</span> (adduser felisa --ingroup profesores)<br /></li>
          <li>Jaime: Que va a ser un usuario normal, por lo que no podrá acceder a la gestión de informatica.ies.org<br /></li>
        </ul><br />
      </td>
    </tr></tbody>
  </table><br /><span style="font-weight: bold;">2) Configuración de Apache2 para la creación de los subdominios</span><br style="font-weight: bold;" /><br />
  <table width="100%" border="1"><tbody>
    <tr>
      <td width="100%" valign="top"><br />1) Instala apache2 y sigue la documentación para crear dos sitios virtuales (Virual Hosting):<br />
        <ul>
          <li>www.ies.org: Que se guardará en /srv/www/ies</li>
          <li>informatica.ies.org: Que se guardará en /srv/www/infomatica</li>
        </ul>Como ejemplo del fichero de configuración de www.ies.org podría quedar:<br /><br /><pre>&lt;VirtualHost *:80&gt;
 ServerAdmin admin@ies.org
 ServerName www.ies.org
 DocumentRoot /srv/www/ies
&lt;Directory /&gt;
 Options FollowSymLinks
 AllowOverride None
&lt;/Directory&gt;
&lt;Directory /srv/www/ies&gt;
 Options Indexes FollowSymLinks MultiViews
 AllowOverride None
 Order allow,deny
 allow from all
&lt;/Directory&gt;

</pre>
        <p>2) Dentro de cada directorio, puedes crear una página index.html donde se de la bienvenida a la página. Prueba desde un navegador que tienes acceso a las dos páginas.<br /></p>
      </td>
    </tr></tbody>
  </table>
  <div style="text-align: justify;"><br /><span style="font-weight: bold;">3) Pasos finales</span><br /><br />
    <table width="100%" border="1"><tbody>
      <tr>
        <td width="100%" valign="top">
          <table width="100%" border="1"><tbody>
            <tr>
              <td width="100%" valign="top"><br />1) Como el usuario admin va a ser el que vamos a utilizar para gestionar www.ies.org desde FTP vamos a modificar el fichero <span style="font-weight: bold;">/etc/passwd </span>para que su home sea /srw/www/ies<br /><br />2) Como la página informatica.ies.org sólo se va a poder gestionar por FTP por los usarios que pertenecen al grupo profesores, el directorio /srv/www/informatica lo tenemos que asignar al grupo profesores y poner los permisos adecuados:<br /><br /><pre># chgrp -R profesores /srv/www/informatica
# chmod -R 770 /srv/www/informatica</pre><br />En el home de felisa tendremos que crear un enlace simbólico a /srv/www/informatica para que desde el ftp pueda acceder al directorio donde está alojada la página informatica.ies.org.<br /><br /><pre># ln -s /srv/www/informatica informatica

</pre>
                <p>Nota: Aunque creemos este enlace simbólico en el home del usuario Jaime, este no podrá aceeder al directorio /srv/www/informatica, ya que al no pertenecer al grupo profesores no tendrá acceso al directorio.<br /></p><br />3) Accede por un cliente FTP con los tres usuarios y prueba las funcionalidades que tienen cada uno.<br /><br />
              </td>
            </tr></tbody>
          </table>
        </td>
      </tr></tbody>
    </table><br /></div><span style="font-weight: bold;"></span><span style="font-weight: bold;"><br /></span></div>
<div style="text-align: justify;"> </div>
