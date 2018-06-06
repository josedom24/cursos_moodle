# Logs: obteniendo información del sistema
<div style="text-align: justify;">
  <h2> ¿Qué es un log(registro)?</h2>
  <p>No es más que una entrada en un fichero donde se detalla el funcionamiento de alguna aplicación del sistema o del propio kérnel, normalmente con el formato &quot;Día Hora Equipo Aplicación: Mensaje&quot;, por ejemplo:</p> <pre>Nov 23 10:10:00 talut dhclient: DHCPREQUEST on eth0 to 10.127.37.28 port 67</pre>
  <p>Estos ficheros se ubican en el directorio <tt>/var/log/</tt>, en diferentes ficheros o en el genérico <tt>/var/log/syslog </tt>(en otras distros <tt>/var/log/messages</tt>) y en general son manejados por el demonio del sistema <tt>syslogd</tt>. Existen también aplicaciones que tienen sus propias aplicaciones de control de estas entradas y sus propios ficheros (directorios) de almacenamiento, como son apache, MySQL, etc.</p>
  <h2>Comprobando el funcionamiento del equipo</h2> A la hora de realizar cualquier modificación en un servicio, es una práctica habitual tener abierto el fichero <tt>syslog</tt> de forma continua. Esto puede realizarse de muchas maneras, por ejemplo con la instrucción: <pre>tail -f /var/log/syslog</pre>
  <table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
    <tr>
      <td width="100%" valign="top"><br />1) Abre dos terminales de tu equipo y colócalas en el escritorio para verlas simultáneamente. Abre en la primera terminal de forma continua el fichero <tt>syslog</tt> y en la otra reinicia alguno de los demonios de la máquina (por ejemplo cron).<br /><br />
        <p></p>
      </td>
    </tr></tbody>
  </table> <br />
  <h2>Prioridad del log</h2>El nivel de detalle de los registro se denomina prioridad y es configurable, los valores de prioridad de menor a mayor son:<br />
  <ol>
    <li>debug</li>
    <li>info</li>
    <li>notice</li>
    <li>warning (warn)<br /></li>
    <li>error (err)</li>
    <li>crit</li>
    <li>alert</li>
    <li>panic (emerg)</li>
  </ol>Si configuramos una aplicación con la prioridad &quot;debug&quot;, aparecerán gran cantidad de registros, de ahí su nombre, ya que se utilizan para depurar el funcionamiento de una aplicación. Por el contrario si configuramos una aplicación con la prioridad &quot;panic&quot; sólo se producirán registros en casos de emergencia.<br /><br />
  <table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
    <tr>
      <td width="100%" valign="top"><br />1)Edita el fichero de configuración del servidor ssh, busca la directiva donde se determina la prioridad de log de ese servicio y modifícala a &quot;debug&quot;.<br /><br />2) Reinicia el servicio y abre de forma continua el fichero <tt>/var/log/auth.log</tt><span style="font-family: monospace;"><br /></span><br />3) Realiza una conexión ssh desde otra sesión y comprueba el detalle de los registros que se generan.<br /><br />4) Vuelve a poner la prioridad al nivel que estaba y reinicia el servicio.
      </td>
    </tr></tbody>
  </table> <br /></div>
