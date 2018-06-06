# Uso de módulos en Apache2: userdir.mod
<div style="text-align: justify;">El objetivo de esta práctica es usar el módulo userdir.mod de apache2 que nos va a permitir que cada usuario tenga un directorio público en su home (public_html) donde guardará su página personal.<br /><br />De esta manera los profesores o alumnos del departamento podrán tener su página personal en la dirección http://informatica.ies.org/~usuario<br /><br />Los módulos se guardan en /etc/<span class="highlightedSearchTerm">apache2</span>/mods-available para activarlo lo que tenemos que hacer es crear los enlaces virtuales a los archivos necesarios dentro del directorio /etc/<span class="highlightedSearchTerm">apache2</span>/mods-enabled.<br /><br />En nuestro caso:<br /><br /><pre># cd /etc/apache2/mods-enabled
# ln -s ../mods-available/userdir.conf userdir.conf
# ln -s ../mods-available/userdir.load userdir.load</pre>
  <p>En este caso el módulo se activa para los dos dominios virtuales, para que solo funcione en informatica.ies.org:</p>
  <table width="100%" border="1"><tbody>
    <tr>
      <td width="100%" valign="top"><br />
        <div style="text-align: justify;">1) Dentro del fichero de configuración del dominio informatica.ies.org incluimos los ficheros necesarios para activar el módulo:<br /><br /><pre># Include /etc/apache2/mods-available/userdir.conf
# Include /etc/apache2/mods-available/userdir.load</pre><br />2) Reinicia el servidor web.<br /><br />3) Crea en el home de un usuario un directorio public_html con los permisos adecuados y un fichero index.html dentro de él. Comprueba desde un navegador que se puede visualizar la página en informatica.ies.org/~usuario<br /></div>
      </td>
    </tr></tbody>
  </table><br />
  <p><br /></p>
  <p><br /></p><br /><br /> </div>
