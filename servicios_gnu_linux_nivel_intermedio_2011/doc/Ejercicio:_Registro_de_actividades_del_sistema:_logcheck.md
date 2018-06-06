# Ejercicio: Registro de actividades del sistema: logcheck
<h1> <font size="5">logcheck</font></h1>Logcheck es una herramienta encargada de revisar periódicamente los logs del sistema y enviar un correo al administrador de lo que sea importante. Logcheck revisa periódicamente los logs del sistema, analizando cada una de las líneas y clasificándola según diferentes niveles de alerta, informando al administrador del sistema en un formato fácil de leer, descartando las líneas que no tengan relevancia, y --típicamente-- enviándolo por correo. Logcheck comprobará cada línea de los logs vigilados contra cuatro niveles de seguridad: Ignorar, actividad inusual, violación de seguridad y ataque. <br /><br />
<h2><font size="4">Instalación y configuración de logcheck</font></h2>
<table border="1" width="100%"><tbody>
  <tr>
    <td width="100%" valign="top"><font size="3"><br /></font>
      <div style="text-align: justify;"><font size="3">1.- Instala el paquete logcheck en avatar<br /><br />2.- El fichero de configuración de logcheck se encuentra en el fichero /etc/logcheck/logcheck.conf, comprueba que el parámetro SENDMAILTO está configurado para enviar las notificaciones al usuario root.<br /><br />3.- Visualiza el fichero /etc/cron.d/logcheck y comprueba cunado se ejecuta por defecto logcheck<br /><br /></font></div>
    </td>
  </tr></tbody>
</table><font size="3"><br /></font>
<h2><font size="4">Envío de correos a direcciones externas</font></h2>
<p><font size="3">Como hemos visto anteriormente el corro de la herramienta logcheck (y de las aplicaciones que vamos a ver más adelante en este mismo tema) mandan los correos electrónicos al root. Normalmente, aunque hagamos muchas tareeas administrativas con el usuario root, nosotros trabajaremos normalmente con un usuario en el servidor con menos privilegios.</font></p>
<p><font size="3">Para redirigir el correo que va dirigido al root a nuestro usuario, podemos modificar el fichero /etc/aliases y añadir la línea:</font></p>
<p><font size="3">root: usuario</font></p>
<p><font size="3">Tan sólo nos queda ejecutar el comando newaliases para que los cambios se lleven a efecto.<br /></font></p>
<p><font size="3">Además si tenemos instalado un servidor SMTP (exim4,postfix) y queremos que esa notificación sea redirigida a una dirección de correo externa, podemos crear en la cuenta de suario un fichero llamado .forward donde indicaremos la cuenta de correo donde queremos recibir la notificación.<br /></font></p>
<p><br /></p>
