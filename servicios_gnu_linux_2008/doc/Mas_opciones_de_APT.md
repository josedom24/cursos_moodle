# Más opciones de APT
<h2 style="text-align: justify;">Actualizando los paquetes de nuestro sistema<br /></h2>
<div style="text-align: justify;"> <pre>apt-get update</pre> Para actualizar la lista de paquetes disponibles con la información del fichero <em>/etc/apt/sources.list</em> <pre>apt-get upgrade</pre>Con esta instrucción actualizamos la instalación de los paquetes a su última versión sin tener en cuenta las dependencias.<br /><br /><pre>apt-get dist-upgrade
</pre>Con esta instrucción actualizamos la instalación de los paquetes a su última versión pero teniendo en cuenta las dependencias.<br /><br />Algunas consideraciones:<br /><br />1) Si estamos trabajando en la rama estable (etch) las dependencias de los paquetes no cambian por lo que es lo mismo usar un upgrade que un dist-upgrade.<br /><br />2) En la versión testing las dependencias pueden ir cambiando por lo que si utilizamos upgrade los paquetes cuyas dependencias han cambiado se retienen y no se actualizan, por lo que es conveniente usar el dist-upgrade para ir resolviendo las dependencias.<br /><br /> </div>
<table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top">Nosotros estamos trabajando con la rama testing (lenny)<br /><br />1) Ejecuta un upgrade y comprueba si existe algún paquete retenido.<br /><br />2) Si existe algún paquete retenido, ejecuta un dist-upgrade para resolver las depedencias.<br /><br />
    </td>
  </tr></tbody>
</table>
<div style="text-align: justify;"><br /> </div>
<h2 style="text-align: justify;">Buscando paquetes en los repositorios: apt-cache</h2>
<div style="text-align: justify;">Con la siguiente instrucciones podemos buscar paquetes en los repositorios:<br /><br /><pre># apt-cache search &lt;busqueda&gt;
</pre> </div>
<p style="text-align: justify;">Busca todos los paquetes que tengan relaciones con las palabras que hayas indicado en la busqueda.</p>
<div style="text-align: justify;"><pre> # apt-cache show &lt;paquete&gt;</pre> Te da información del paquete indicado, si tienes instalado el paquete te da información del instalado y de la nueva versión.<pre> # apt-cache showpkg &lt;paquete&gt; </pre> Te da información más detallada del paquete indicado.<br /><br /><pre># apt-cache depends <span style="font-family: verdana,arial,helvetica,sans-serif;">&lt;paquete&gt;</span> </pre>Te da la lista de dependencias del paquete indicado.<br /><br /><br /> </div>
<table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />1) Busca todos lo paquetes que tengan la palabra &quot;apache2&quot;<br /><br />2) Obtén información del paquete ssh que hemos instalado<br /><br />3) Lista los paquetes de los que depende el paquete phpmyadmin<br /><br /><br />
    </td>
  </tr></tbody>
</table>
<div style="text-align: justify;"> </div>
<h2 style="text-align: justify;">Aptitude</h2>
<div style="text-align: justify;">Siguiendo el manual de Aptitude realiza las siguientes tareas:<br /><br /> </div>
<table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />1) Busca paquetes que tengan la palabra &quot;ldap&quot;<br /><br />2) Desinstala el paquete &quot;ssh&quot; que habiamos instalado anteriormente.<br /><br />3) Instala un paquete.<br /><br />4) Aptitude también se puede usar desde la línea de comandos: realiza una instalación, una eliminación, una búsqueda, una actualización del sistema y una actualización de la lista de paquetes desde la línea de comandos usando aptitude.<br /><br />5) ¿Cuál es la diferencia más importante entre usar aptitude y apt?<br /><br />
    </td>
  </tr></tbody>
</table>
<div style="text-align: justify;"><br /><br /> </div>
<h2 style="text-align: justify;"><br /> </h2>
