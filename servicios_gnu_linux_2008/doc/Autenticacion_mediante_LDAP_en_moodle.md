# Autenticación mediante LDAP en moodle
<div style="text-align: justify;"> Muchos CMS incluyen módulos para diferentes mecanismos de autenticación, como un ejemplo de ellos veremos la autenticación de usuarios en moodle sobre LDAP. La ventaja principal de esto es que permite tener un sistema único de auntenticación para todas las aplicaciones de una organización.<br /><br />Vamos a seguir los pasos que se describen en &quot;LDAP Authentication&quot; de la documentación oficial de Moodle y que aparece en Enlaces recomendados.<br /><br />Entramos en moodle con el perfil de administrador y vamos a Administración del sitio&gt;&gt;Usuarios&gt;&gt;Autenticación&gt;&gt;Administrar autenticación y en la tabla que aparece activamos &quot;Usar un servidor LDAP&quot; y hacemos click en Configuración.<br /><br />Obtendremos la pantalla en la que tendremos que introducir todos los datos de la conexión con el servidor y las características de nuestros usuarios.<br /><br />La mayoría de las opciones están claras y bien explicadas en la documentación, sólo vamos a comentar las que presentan dudas.<br /> </div>
<h4 style="text-align: justify;">Ajustes de servidor LDAP</h4>
<div style="text-align: justify;"> </div>
<p style="text-align: justify;">(Sin comentarios)<br /></p>
<div style="text-align: justify;"> </div>
<h4 style="text-align: justify;">Fijar ajustes</h4>
<div style="text-align: justify;"> </div>
<p style="text-align: justify;">Hay que especificar el dn del usuario que se conecta al LDAP (por ejemplo admin), debe ser alguno que tenga como mínimo permiso de lectura sobre los atributos &quot;userPassword&quot; y de lectura y escritura si queremos que se puedan modificar las contraseñas desde moodle.<br /></p>
<div style="text-align: justify;"> </div>
<h4 style="text-align: justify;">Ajustes de búsqueda de usuario </h4>
<div style="text-align: justify;">Tipo de usuario (posixAccount)<br />Contexto es el dn de la rama que contiene los usuarios (la unidad organizativa People por ejemplo).<br />Buscar subcontextos: Sí<br />Atributo del usuario: uid (porque usamos posixAccount)<br /><br /> </div>
<h4 style="text-align: justify;">Forzar cambio de contraseña </h4>
<div style="text-align: justify;">(Sin comentarios) </div>
<h4 style="text-align: justify;">Ajustes de caducidad de la contraseña LDAP. </h4>
<div style="text-align: justify;">(Sin comentarios) </div>
<h4 style="text-align: justify;">Habilitar creación por parte del usuario </h4>
<div style="text-align: justify;">(Sin comentarios) </div>
<h4 style="text-align: justify;">Creador de curso </h4>
<div style="text-align: justify;">(Sin comentarios) </div>
<h4 style="text-align: justify;">Script de sincronización del Cron </h4>
<div style="text-align: justify;">(Sin comentarios) </div>
<h4 class="main" style="text-align: justify;">Mapeado de datos</h4>
<div style="text-align: justify;">Estos campos varían mucho de un directorio LDAP a otro, por lo que tendremos que especificar el nombre de los atributos en nuestro caso para que Moodle los pueda encontrar. Por ejemplo:<br /><br />Dirección de correo -&gt; mail<br />Teléfono 1-&gt; telephoneNumber<br /><br />Etcétera<br /><br />Finalmente le damos a guardar cambios e intentamos acceder a moodle con un usuario que tengamos en el directorio LDAP.<br /></div>
