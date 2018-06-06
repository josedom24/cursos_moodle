# Configuración de awstats para virtual hosting
<div style="text-align: justify;"> En la documentación que ofrecemos se muestra como instalar awstats en unservidor web. En esta práctica queremos configurar el sistema para que cada subdominio genere estadísticas separadas.<br /><br /> </div>
<table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />1) Modifica los ficheros de configuración de los subdominios para que los logs lo escribe en ficheros distintos, por ejemplo:
      <ul>
        <li>www.ies.org, guarde los logs en /var/log/apache2/access_ies.log</li>
        <li>informatica.ies.org, guarde los logs en /var/log/aapache2/access_inf.log</li>
      </ul>Por ejmplo:<br /><br /><pre> CustomLog /var/log/apache2/access_ies.log combined</pre>La opción combined ofrece información adicional (SO, navegador, ...) del cliente en el log.<br /><br />2) Crea dos ficheros de configuración distintos para awstats para cada nombre de dominio.<br /><br />3) Ahora tienes que generar los ficheros de estadísticas dos veces, utlizando los distintos ficheros de configuración que has creado.<br />
    </td>
  </tr></tbody>
</table>
<div style="text-align: justify;"><br /> </div>
