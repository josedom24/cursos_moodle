# Instalación de un CMS: Moodle
<div style="text-align: justify;">En esta práctica vamos a instalar un gestor de contenido especializado para entornos educativo como es Moodle. Moodle está implementado con PHP y necesita una base de datos para guardar información.<br /></div><br />
<table width="100%" border="1"><tbody>
  <tr>
    <td width="100%" valign="top"><br />
      <div style="text-align: justify;">1) Siguiendo la documentación aportada instala php5 y mysql.<br /><br />2) Descarga la última versión de moodle:<br /><pre>wget http://download.moodle.org/download.php/stable19/moodle-weekly-19.tgz

</pre> </div>
      <div style="text-align: justify;">
        <div style="text-align: justify;">3) Descomprime el fichero en el directorio /srv/www/ies/moodle y desde un navegado accede a http://www.ies.org/moodle e instala moodle siguiendo la documentación aportada.<br /></div><br />4) Podemos hacer una redirección para cuando entremos en www.ies.org se acceda directamente a moodle, una forma de hacerlo es mediante Php. Crea un fichero index.php en la ráiz del sitio (/srv/www/ies) con el siguiente código:<br /><pre>&lt;? Header(&quot;Location:http://www.ies.org/moodle&quot;); ?&gt;</pre></div>
    </td>
  </tr></tbody>
</table><br />
<div style="text-align: justify;"> </div>
