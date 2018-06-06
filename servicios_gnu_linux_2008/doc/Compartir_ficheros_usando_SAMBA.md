# Compartir ficheros usando SAMBA
<div style="text-align: justify;"><span style="font-weight: bold;">1. Instalación de SAMBA</span><br /><br />Simplemente:<br /><pre># apt-get install samba</pre></div>
<div style="text-align: justify;"> </div>
<p style="text-align: justify;">Durante la instalación se nos pregunta en que grupo de trabajo o dominio se va a unir nuestra máquina. Se nos pregunta también si queremos compatibilidad con WINS a lo que respondemos que No.</p>
<div style="text-align: justify;"> </div>
<div> </div>
<p style="text-align: justify;">
  <table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
    <tr>
      <td width="100%" valign="top"><br />1) Instala en mortadelo un servidor Samba.<br /><br />
      </td>
    </tr></tbody>
  </table><br /></p>
<div style="text-align: justify;"><span style="font-weight: bold;">2. Configuración de Samba</span><br /><span style="font-weight: bold;"></span><br /><span style="font-weight: bold;"></span>El fichero de configuración de Samba es /etc/samba/smb.conf y está formado por diferentes secciones (que se indican mediante [seccion]) de las que especificaremos las principales directivas<br /><br />[global]<br /><br /> workgroup = MIGRUPO # Especifica el grupo de trabajo o dominio<br /> server string = %h server # Identificación del servidor<br />; security = ???? # Tipo de autenticación<br /><br />En este curso no vamos a ver la configuración de Samba dentro de un dominio, sino simplemente dentro de un grupo de trabajo para compartir ficheros, por lo que hay dos opciones de security útiles:<br />
  <ul>
    <li>security = user: Es necesario utilizar un nombre de usuario y contraseña de samba en la conexión inicial.</li>
    <li>security = share: Es necesario utilizar una contraseña para cada recurso compartido.<br /></li>
  </ul></div>
<div style="text-align: justify;">Ahora empezamos con las secciones de cada recurso compartido, por ejemplo para compartir algunos directorios basta con hacer:<br /><br />[fotos]<br />path = /home/fotos<br /><br />[videos]<br />comment = Vídeos compartidos<br />path = /home/felisa/videos<br /><br />Para compartir impresoras hay que tener en cuenta que las impresoras se comparten de modo predeterminado, así que solo hay que realizar algunos ajustes. Si se desea que se pueda acceder hacia la impresora como usuario invitado sin clave de acceso, basta con añadir <b>public = Yes</b> en la sección de impresoras del siguiente modo:<br /><br /><pre>[printers]
 comment = All Printers
 path = /var/spool/samba
 printable = yes
 public = yes
 writable = no
 create mode = 0700

</pre> </div>
<p style="text-align: justify;">Para compartir directorios en el mismo fichero de configuración encontrará distintos ejemplos para distintas situaciones particulares. En general, puede utilizar el siguiente ejemplo que funcionará para la mayoría:</p>
<div style="text-align: justify;"> </div>
<div align="center">
  <div style="text-align: justify;"> </div>
  <div> </div><center>
  <div style="text-align: justify;"><pre>[Lo_que_sea]
 comment = Comentario que se le ocurra
 path = /cualquier/ruta/que/desee/compartir</pre></div></center> </div>
<p style="text-align: justify;">El directorio compartido puede utilizar cualquiera de las siguientes opciones:</p>
<table width="85%" cellspacing="0" cellpadding="4" border="1" bgcolor="#e6e6e6" style="border-color: black;"><tbody>
  <tr>
    <th width="30%" valign="top" align="left">Opción
    </th>
    <th width="70%" valign="top" align="left">Descripción
    </th>
  </tr>
  <tr>
    <td width="30%" valign="top" align="left"><code>guest ok</code>
    </td>
    <td width="70%" valign="top" align="left">Define si ser permitirá el acceso como usuario invitado. El valor puede ser <code>Yes</code> o <code>No</code>.
    </td>
  </tr>
  <tr>
    <td width="30%" valign="top" align="left"><code>public</code>
    </td>
    <td width="70%" valign="top" align="left">Es un <b>equivalente</b> del parámetro <b>guest ok</b>, es decir define si ser permitirá el acceso como usuario invitado. El valor puede ser <code>Yes</code> o <code>No</code>.
    </td>
  </tr>
  <tr>
    <td width="30%" valign="top" align="left"><code>browseable</code>
    </td>
    <td width="70%" valign="top" align="left">Define si se permitirá mostrar este recurso en las listas de recursos compartidos. El valor puede ser <code>Yes</code> o <code>No</code>.
    </td>
  </tr>
  <tr>
    <td width="30%" valign="top" align="left"><code>writable</code>
    </td>
    <td width="70%" valign="top" align="left">Define si se permitirá la escritura. Es el parámetro contrario de <code>read only</code>. El valor puede ser <code>Yes</code> o <code>No</code>. Ejemplos: <code>«writable = Yes»</code> <b>es lo mismo que</b> <code>«read only = No»</code>. Obviamente <code>«writable = No»</code> <b>es lo mismo que</b> <code>«read only = Yes»</code>
    </td>
  </tr>
  <tr>
    <td width="30%" valign="top" align="left"><code>valid users</code>
    </td>
    <td width="70%" valign="top" align="left">Define que usuarios o grupos pueden acceder al recurso compartido. Los valores pueden ser nombres de usuarios separados por comas o bien nombres de grupo antecedidos por una @. Ejemplo: <code>fulano, mengano, @administradores</code>
    </td>
  </tr>
  <tr>
    <td width="30%" valign="top" align="left"><code>write list</code>
    </td>
    <td width="70%" valign="top" align="left">Define que usuarios o grupos pueden acceder con permiso de escritura. Los valores pueden ser nombres de usuarios separados por comas o bien nombres de grupo antecedidos por una @. Ejemplo: <code>fulano, mengano, @administradores</code>
    </td>
  </tr>
  <tr>
    <td width="30%" valign="top" align="left"><code>admin users</code>
    </td>
    <td width="70%" valign="top" align="left">Define que usuarios o grupos pueden acceder con permisos administrativos para el recurso. Es decir, podrán acceder hacia el recurso realizando todas las operaciones como super-usuarios. Los valores pueden ser nombres de usuarios separados por comas o bien nombres de grupo antecedidos por una @. Ejemplo: <code>fulano, mengano, @administradores</code>
    </td>
  </tr>
  <tr>
    <td width="30%" valign="top" align="left"><code>directory mask</code>
    </td>
    <td width="70%" valign="top" align="left">Es lo mismo que <code>directory mode</code>. Define que permiso en el sistema tendrán los subdirectorios creados dentro del recurso. Ejemplos: <code>1777</code>
    </td>
  </tr>
  <tr>
    <td width="30%" valign="top" align="left"><code>create mask</code>
    </td>
    <td width="70%" valign="top" align="left">Define que permiso en el sistema tendrán los nuevos ficheros creados dentro del recurso. Ejemplo: <code>0644</code>
    </td>
  </tr></tbody>
</table><br />
<div style="text-align: justify;">Por ejemplo si quieres compartir el directorio público de un servidor FTP, que se almacene en /home/ftp, la configuración quedaría:<br /><pre>[ftp]
 comment = Directorio del servidor FTP
 path = /home/ftp
 guest ok = Yes
 read only = Yes
 directory mask = 0755
 create mask = 0644</pre><br /> </div>
<table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />1) Configura SAMBA para compartir dos directorios:<br /><br />
      <ul>
        <li>/home/curso/public: Que sea accesible desde todas las máquinas con permisos de lectura y escritura.</li>
        <li>/srv/www/ies: Que sea accesible sólo por Felisa y de sólo lectura.</li>
      </ul><br />
    </td>
  </tr></tbody>
</table>
<div style="text-align: justify;"><br /><span style="font-weight: bold;">3. Accediendo a los recursos compartidos</span><br /><span style="font-weight: bold;"></span><br /><span style="font-weight: bold;"></span>Desde el cliente podemos acceder a los recursos compartidos por el servidor montando el sistema de fichero:<br /><br /><code>mount -t cifs -o username=el_necesario,password=el_requerido //alguna_maquina/algún_volumen /punto/de/montaje/</code><br /><code></code><br /><code></code><code></code> </div>
<p style="text-align: justify;">Nota: Es necesario tener instalado el paquete smbfs para poder montar y desmontar directorios compartidos con Samba.</p>
<div style="text-align: justify;"><br /> </div>
<p style="text-align: justify;">Si queremos que estos cambios sean definitivos y se realicen cada vez que arranquemos la máuina tenem,os que añadir en el fichero /etc/fstab otro punto de montaje:</p>
<div style="text-align: justify;"><br /><code>IP_REMOTA:/directorio/compartido /directorio/local </code><code>smbfs user,auto,guest,ro,gid=100 0 0</code><br /> <br /> </div>
<table width="100%" border="1"><tbody>
  <tr>
    <td width="100%" valign="top">
      <div style="text-align: justify;"><br />1) Monta los dos directorios que has compartido con mount y comprueba que funciona. Cambia el modo de seguridad con la opción user y share y comprueba las diferencias.<br /><br />2) Modifica el fichero /etc/fstab para que se monten los directorios cada vez que encedemos la máquina.<br /><br />3) Comprueba desde un entorno gráfico que tienes acceso a los recursos compartidos:<br /> </div>
      <ul>
        <li style="text-align: justify;">Desde el navegador firefox accede a la dirección: smb://ip_servidor_samba/recurso</li>
        <li style="text-align: justify;">Desde Lugares -&gt;Conectar con el servidor...-&gt; Lugar personalizado, y poniendo la dirección anterior.<br /></li>
      </ul>
    </td>
  </tr></tbody>
</table><br />
