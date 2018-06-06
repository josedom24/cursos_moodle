# Cortafuegos con iptables con política por defecto DROP
<div style="text-align:left;"> Sube un fichero de texto (.txt) con las líneas de iptables necesarias para crear un cortafuegos con las siguientes características:<br /></div>
<ul style="text-align:left;"><li>Cliente puede acceder utilizar los protocolos HTTPS, SMTP, DNS, POP3 y LDAP</li> 
  <li>Cliente tiene redireccionados los puertos 4662/tcp y 4672/udp para poder utilizar un programa tipo eMule/aMule.</li> 
  <li>Cliente utiliza el protocolo HTTP mediante proxy transparente con squid</li> 
</ul><div style="text-align:left;">Añade en el fichero con todas las reglas la salida de las instrucciones después de haber probado todos los protocolos desde cliente:<br /></div><br /><div style="text-align:left;"><pre>iptables -t nat -L -n -v
iptables -L -n -v</pre></div>
