# Ejercicio: Instalación y configuración de squid
<p style="font-weight: bold; text-align: justify;">Instalación del proxy-cache squid<br /></p>
<div> </div>
<table border="1" width="100%" style="text-align: left; margin-left: auto; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />
      <div style="text-align: justify;">1. Instala el paquete squid en avatar<br /></div><br />
    </td>
  </tr></tbody>
</table>
<div style="text-align: right;"><br />
  <div style="text-align: justify;"><span style="font-weight: bold;">Configuración del proxy-cache squid</span><br /></div><br />
  <div style="text-align: justify;">Vamos a realizar la configuración inicial de squid indicando algunos parámetros que pueden mejorar el funcionamiento de la caché:<br /></div><br /> </div>
<table border="1" width="100%"><tbody>
  <tr>
    <td width="100%" valign="top" style="text-align: right;"><br />
      <div style="text-align: justify;">1. Cambia la cantidad de memoria RAM asignada al funcionamiento de squid (cache_mem) a 64 MB.<br />2. Cambia el tamaño máximo de los ficheros que va a guardar (maximum_object_size) a 20 MB.<br />3. Cambia el tamaño de la cahe a 500 MB (cache_dir)<br />4. Vamos a darle acceso a los ordenadores que están en nuestra red local para ello vamos a crear una regla acl:<br /><br /><pre>acl hostpermitidos src 192.168.2.0/24</pre>Y a continuación vamos a darle acceso con<br /><br /><pre>http_access allow hostpermitidos</pre>Esta última directiva irá delante de http_access deny all<br /><br />4. Reinicia el demonio squid<br /><br /> </div>
    </td>
  </tr></tbody>
</table><br />
<div style="text-align: justify;">Recuerda que las # indican comentarios, por lo tantos las debes quitar para que tengan efecto las modificaciones.<br /></div><br />
<div style="text-align: justify;"><span style="font-weight: bold;">Configuración del cliente para acceder a internet a través de squid</span><br /><br />En el navegador Mozilla-firefox del cliente, seleccionamos Editar-&gt;Preferencias-&gt;Avanzado-&gt;Red-&gt;Configuración-&gt;Configuración Manual del Proxy y en los distintos protocolos ponemos el host correspondiente (avatar.example.com) con el puerto 3128 que es por el que escucha el squid peticiones de sus clientes. Podemos ponerlo en todos los protocolos menos en el socks.<br /><br />
  <table border="1" width="100%"><tbody>
    <tr>
      <td width="100%" valign="top"><br />1. Configura el navegador web del cliente, para que utilice el proxy-cache squid de avatar.<br />2. Comprueba el acceso del cliente a internet monitorizando el fichero de log de squid /var/log/squid3/access.log<br /><br />Puedes utilizar la siguiente instrucción para ver el contenido de ese fichero en tiempo real:<br /><pre>tail -f /var/log/squid3/access.log</pre><br />Los posibles códigos que nos podemos encontrar en las líneas de ese fichero de log son los siguientes:<br />
        <ul>
          <li>
            <div class="FORMALPARA">
              <p><b>TCP_MISS. </b>Indica que el objeto solicitado no estaba en la cache.</p></div></li>
          <li>
            <div class="FORMALPARA">
              <p><b>TCP_HIT. </b>Nos informa de que teníamos en cache una copia válida del objeto que se había pedido. Este mensaje indica que el objeto solicitado estaba en nuestra cache pero había expirado. Realizamos una petición para comprobar si el objeto que contiene nuestra cache es todavía válido. La respuesta nos indica que no ha sido modificado desde que realizamos la anterior petición y por lo tanto se produce un acierto en cache.</p></div></li>
          <li>
            <div class="FORMALPARA">
              <p><b>TCP_REFRESH_MISS. </b>El objeto solicitado estaba en cache pero su timeout había expirado por lo que se realiza una petición para comprobar si el objeto ha sido modificado desde la petición anterior. La respuesta contiene el nuevo objeto indicando que el objeto que contenía nuestra cache era antiguo y por lo tanto se produce un fallo en cache.</p></div></li>
          <li>
            <div class="FORMALPARA">
              <p><b>TCP_MEM_HIT. </b>Indica que el objeto solicitado residía en cache y tambíén en memoria por lo que no se tiene que leer del disco,y por lo tanto, se produce un acierto.</p></div></li>
        </ul><br /><br />
      </td>
    </tr></tbody>
  </table><br /><br /> </div>
