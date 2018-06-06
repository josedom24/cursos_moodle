# Avatar como servidor de correo de los clientes de nuestra red
<style type="text/css"> &amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;lt;!-- @page { margin: 2cm } P { margin-bottom: 0.21cm } A:link { color: #0000ff } --&amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;amp;gt; </style>
<ul>
  <ul>
    <ul>
      <ul>
        <li>
          <div style="text-align: left;"> <font color="#000000"><font size="3"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"><span style="font-weight: bold;">Figura</span>: a la figura anterior le añadimos 2 situaciones más, los <span style="text-decoration: underline;">casos 4 y 5</span>.</span></span></font></font></font></font></font></font></div></li>
      </ul>
    </ul>
  </ul>
</ul>
<div style="margin-left: 40px;">
  <div style="margin-left: 40px;"><font color="#000000"><font size="3"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">
    <table border="1" style="width: 988px; height: 464px;"><tbody>
      <tr>
        <td width="100%" valign="top"><img width="1163" vspace="0" hspace="0" height="454" border="0" src="../img/correo$@SLASH@$RedServicioCorreo-ClientesRed.jpeg" alt="Casos 4 y 5" title="Casos 4 y 5" />
        </td>
      </tr></tbody>
    </table></span></span></font></font></font></font></font></font></div><br /><font color="#000000"><font size="3"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"><br /></span></span></font></font></font></font></font></font></div><font color="#000000"><font size="3"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"><br /></span></span></font></font></font></font></font></font>
<ul>
  <ul>
    <ul>
      <ul>
        <li>
          <p align="justify" style="margin-bottom: 0cm;" class="western"> <font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><font face="Times New Roman, serif"><font size="2"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">El <span style="font-weight: bold;">objetivo</span> de este apartado es la <span style="font-style: italic; font-weight: bold;">configuración en equipos cliente de nuestra red MZ para posibilitar el envío de correo entre usuarios de nuestro dominio.</span></span></span></font></font></font></font></font></font></p></li><br />
      </ul>
    </ul>
  </ul>
</ul><hr style="width: 100%; height: 2px;" />
<ul>
  <ul>
    <ul>
      <ul><br />
        <li>
          <p align="justify" style="margin-bottom: 0cm;" class="western"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><font face="Times New Roman, serif"><font size="2"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"></span></span></font></font><span style="text-decoration: none;"><b><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">Caso 4</span></b></span></font></font></font></font><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">: <span style="font-weight: bold;">Envío de correo desde el cliente a usuarios del dominio avatar.doesntexist.org.</span></span></span></span></span></font></font></font></font></p></li>
        <ul>
          <li>
            <p align="justify" style="margin-bottom: 0cm;" class="western"><font color="#0000ff"><font color="#000000"><font face="Nimbus Roman No9 L, serif"><font size="2"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"><span style="text-decoration: underline;">Paso previo</span>. Debemos habilitar el envío de correo desde cliente de nuestra red. Para ello añade 192.168.1.0/24 en la directiva mynetworks, quedando:</span></span></span></span></font></font></font></font></p></li>
        </ul>
      </ul>
    </ul>
  </ul>
</ul>
<p align="justify" style="margin-bottom: 0cm; margin-left: 280px;" class="western"><font color="#0000ff"><font color="#000000"><font face="Nimbus Roman No9 L, serif"><font size="2"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"></span></span></span></span></font><font size="1" style="font-size: 8pt;"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">mynetworks = 127.0.0.0/8 [::ffff:127.0.0.0]/104 [::z1] </span></span></span></span></font></font></font></font><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="1" style="font-size: 8pt;"><span style="font-style: normal;"><span style="text-decoration: none;"><b><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">192.168.1.0/24</span></b></span></span></font></font></font></font> </p>
<ul>
  <ul>
    <ul>
      <ul>
        <ul>
          <li style="text-align: left;">
            <p style="margin-bottom: 0cm;" class="western"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="1" style="font-size: 8pt; font-weight: bold;"><span style="font-style: normal;"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"></span></span></span></font><font size="2"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"><span style="font-weight: bold;">Cliente</span>: Usaremos como cliente, en primer lugar, una <span style="font-weight: bold;">conexión telnet</span> (poco vistosa y nada usada por los usuarios, pero muy interesante tanto para entender los pasos que sigue el protocolo SMTP (y otros) y para un administrador de redes).</span></span></span></span></font></font></font></font></p></li>
        </ul>
      </ul>
    </ul>
  </ul>
</ul>
<table border="1" style="width: 622px; height: 471px; margin-left: 200px;"><tbody>
  <tr>
    <td width="100%" valign="top"><img width="617" vspace="0" hspace="0" height="461" border="0" src="../img/correo$@SLASH@$Caso4-clientecomandos.jpg" alt="Comandos SMTP" title="Comandos SMTP" /><br />
    </td>
  </tr></tbody>
</table><br />
<ul>
  <ul>
    <ul>
      <ul>
        <ul>
          <li style="text-align: left;">
            <p style="margin-bottom: 0cm;" class="western"> <font color="#000000"><font size="2"><font color="#0000ff"><font color="#000000"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">En la figura anterior observa los pasos del protocolo SMTP (ten en cuenta que estos pasos se siguen en cualquier de los 5 casos explicados, pero se introducen en este apartado al conectar en modo comando con telnet). Pasemos a describirlos.</span></span></span></span></font></font></font></font> </p></li>
        </ul>
      </ul>
    </ul>
  </ul>
</ul>
<ul>
  <ul>&nbsp;
  </ul>
</ul>
<ul>
  <ul>
    <ul>
      <ul>
        <ul>
          <ul>
            <li>
              <p lang="es-ES" align="justify" style="margin-bottom: 0cm;" class="western"><font color="#000000"><font size="2"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><span style="font-style: normal;"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"><span style="text-decoration: underline;">Esquema general</span>:</span></span></span></font></font></font></font></font><br /> </p></li>
          </ul>
        </ul>
      </ul>
    </ul>
  </ul>
</ul>
<table border="1" style="width: 375px; height: 30px; margin-left: 240px;"><tbody>
  <tr>
    <td width="100%" valign="top"><img width="370" vspace="0" hspace="0" height="130" border="0" title="Esquema General SMTP" alt="Esquema General SMTP" src="../img/correo$@SLASH@$Caso4-FaseGeneral.jpg" /><br />
    </td>
  </tr></tbody>
</table><br />
<ul>
  <ul>
    <ul>
      <ul>
        <ul>
          <ul>
            <li>
              <p lang="es-ES" align="justify" style="margin-bottom: 0cm;" class="western"><font color="#000000"><font size="2"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><span style="font-style: normal;"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"></span></span></span></font></font></font><span style="text-decoration: underline;">Fases en el envío de un mensaje de correo</span></font></font></p></li>
          </ul>
          <ul>
            <ol>
              <li style="text-align: left;"> <font color="#000000"><font size="2"><u>Fase de autenticación</u> (puede haber otra si la sesión es cifrada). El cliente lanza los comandos siguientes para indicar qué usuario envía el correo, y a quién va dirigido. En nuestro ejemplo el cliente no llega a autenticarse al no estar configurado el servidor de correo para ello, tan sólo se intercambian estos mensajes. </font></font>
                <p lang="es-ES" style="margin-bottom: 0cm;" class="western"><font color="#000000"><font size="2">
                  <table rules="none" frame="void" border="0" style="border-style: none; width: 435px; height: 142px; background-image: none; float: none; text-align: left; vertical-align: top;"><tbody>
                    <tr>
                      <td width="100%" valign="top">
                        <div style="text-align: left;"> </div>
                        <ul>
                          <li><font size="1" color="#000000">EHLO o HELO “cadena presentándose el cliente ante el servidor”</font></li>
                          <li><font size="1" color="#000000">MAIL FROM: “dirección de correo del remitente”</font></li>
                          <li><font size="1" color="#000000">RCPT TO: “dirección de correo del destinatario”</font></li>
                        </ul><font size="1" color="#000000"><br /></font><br /><font color="#000000"><font size="2">Una vez autenticado hay que componer el mensaje y enviar</font></font>
                      </td>
                    </tr></tbody>
                  </table></font></font></p></li>
              <li style="text-align: left;">
                <p lang="es-ES" style="margin-bottom: 0cm;" class="western"><font color="#000000"><font size="2"><u>Fase de envío del mensaje</u>.</font></font></p></li>
              <ol>
                <li>
                  <p lang="es-ES" align="justify" style="margin-bottom: 0cm;" class="western"><font color="#000000"><font size="2">El cliente lanza la orden <font size="1">DATA</font> y el servidor responde indicando “354 End data with &lt;CR&gt;&lt;LF&gt;.&lt;CR&gt;&lt;LF&gt;”, lo que quiere decir que cuando el cliente finalice el mensaje y desee enviarlo debe escribir un punto y dar un retorno de carro, es decir, una vez a la tecla intro.</font></font></p></li>
                <li>
                  <p lang="es-ES" align="justify" style="margin-bottom: 0cm;" class="western"><font color="#000000"><font size="2">El cliente lanza las cadenas</font></font></p></li>
                <ol style="font-family: trebuchet ms,verdana,arial,helvetica,sans-serif;">
                  <li>
                    <p lang="es-ES" align="justify" style="margin-bottom: 0cm;" class="western"><font size="1" color="#000000">From: “dirección del remitente” + SALTO DE LÍNEA (ie intro)</font></p></li>
                  <li>
                    <p lang="es-ES" align="justify" style="margin-bottom: 0cm;" class="western"><font size="1" color="#000000">To: “dirección del destinatario” + SALTO DE LÍNEA (ie intro)</font></p></li>
                  <li>
                    <p lang="es-ES" align="justify" style="margin-bottom: 0cm;" class="western"><font size="1" color="#000000">Cc: “dirección del destinatario” para tener una copia + SALTO DE LÍNEA (ie intro)</font></p></li>
                  <li>
                    <p lang="es-ES" align="justify" style="margin-bottom: 0cm;" class="western"><font size="1" color="#000000">Bcc: “dirección del destinatario” para tener una copia ciega</font></p></li>
                  <li>
                    <p lang="es-ES" align="justify" style="margin-bottom: 0cm;" class="western"><font size="1" color="#000000">Date: “fecha” + SALTO DE LÍNEA (ie intro)</font></p></li>
                  <li>
                    <p lang="es-ES" align="justify" style="margin-bottom: 0cm;" class="western"><font size="1" color="#000000">Subject: “asunto” + SALTO DE LÍNEA (ie intro)</font></p></li>
                  <li>
                    <p lang="es-ES" align="justify" style="margin-bottom: 0cm;" class="western"><font size="1" color="#000000">MIME-Versión: “valor de la versión de MIME usada” + SALTO DE LÍNEA (ie intro)</font></p></li>
                  <li>
                    <p lang="es-ES" align="justify" style="margin-bottom: 0cm;" class="western"><font size="1" color="#000000">Otras cabeceras + SALTO DE LÍNEA (ie intro)</font></p></li>
                  <li>
                    <p lang="es-ES" align="justify" style="margin-bottom: 0cm;" class="western"><font size="1" color="#000000">DOS SALTOS DE LÍNEAS</font></p></li>
                  <li>
                    <p align="justify" style="margin-bottom: 0cm;" class="western"><font size="1" color="#0000ff"><font color="#000000">Escribe el mensaje en varias líneas</font></font></p></li>
                  <li>
                    <p align="justify" style="margin-bottom: 0cm;" class="western"><font size="1" color="#0000ff"><font color="#000000"><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">DOS SALTOS DE LÍNEAS, y en el segundo escribe “.” para finalizar el mensaje, y el cliente lo envía al servidor</span></span></span></span></span></font></font></p></li>
                </ol>
              </ol>
            </ol>
          </ul>
          <li>
            <p align="justify" style="margin-bottom: 0cm;" class="western"><font color="#0000ff"><font color="#000000"><span style="text-decoration: none;"><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"></span></span></font></font><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"><span style="font-weight: bold;">Servidor Avatar</span>: lista de mensajes recibidos.</span></span></span></span></span></font></font></font></font></p></li>
        </ul>
      </ul>
    </ul>
  </ul>
</ul>
<table border="1" style="width: 773px; height: 132px; margin-left: 200px;"><tbody>
  <tr>
    <td width="100%" valign="top"><img width="773" vspace="0" hspace="0" height="122" border="0" title="Recepcion correo del caso 4" alt="Recepcion correo del caso 4" src="../img/correo$@SLASH@$Caso4-Env%C3%ADoComandos-ListaEnAvatar.jpg" /><br />
    </td>
  </tr></tbody>
</table><br /><br /><br /><hr style="width: 100%; height: 2px;" /><br />
<ul>
  <ul>
    <ul>
      <ul>
        <ul>
          <li>
            <p align="justify" style="margin-bottom: 0cm;" class="western"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">Por último, usaremos un <span style="font-weight: bold;">cliente gráfico</span>, en nuestro caso <span style="font-style: italic;">Evolution</span>. Evolution es el cliente gráfico clásico para el envío del correo -similar a las versiones Outlook de Microsoft y otras de Linux-.</span></span></span></span></font></font></font></font></p></li>
          <ul>
            <li>
              <p align="justify" style="margin-bottom: 0cm;" class="western"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"><span style="font-weight: bold;">Cliente</span>. Lo primero que haremos será configurar una cuenta de correo</span></span></span></span></font></font></font></font></p></li>
            <ul>
              <li>
                <p align="justify" style="margin-bottom: 0cm;" class="western"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">En nuestro programa Evolution accederemos a menú --&gt; preferencias. <font size="1"><span style="font-style: italic;">Observése el uso intencionado de la interfaz en inglés como recurso para potenciar el programa de bilingúismo (el hábito hace al monje).</span></font></span></span></span></span></font></font></font></font></p></li>
              <li>
                <p align="justify" style="margin-bottom: 0cm;" class="western"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">Añadiremos una cuenta cuya configuración será:</span></span></span></span></font></font></font></font></p></li>
            </ul>
          </ul>
        </ul>
      </ul>
    </ul>
  </ul>
</ul>
<table border="1" style="width: 547px; height: 532px; margin-left: 240px;"><tbody>
  <tr>
    <td width="100%" valign="top"><img width="537" vspace="0" hspace="0" height="522" border="0" src="../img/correo$@SLASH@$caso4-grafico-Identidad.png" alt="Configuracion Evolution. Identidad" title="Configuracion Evolution. Identidad" /><br />
    </td>
  </tr></tbody>
</table>
<table border="1" style="width: 543px; height: 532px; margin-left: 240px;"><tbody>
  <tr>
    <td width="100%" valign="top"><img width="537" vspace="0" hspace="0" height="522" border="0" src="../img/correo$@SLASH@$caso4-grafico-Sending.png" alt="Cliente gráfico. Configuración identidad" title="Cliente gráfico. Configuración identidad" /><br />
    </td>
  </tr></tbody>
</table><br />
<ul>
  <ul>
    <ul>
      <ul>
        <ul>
          <ul>
            <ul>
              <li>
                <p align="justify" style="margin-bottom: 0cm;" class="western"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">Componemos el mensaje y enviamos</span></span></span></span></font></font></font></font></p></li>
            </ul>
          </ul>
        </ul>
      </ul>
    </ul>
  </ul>
</ul>
<table border="1" style="width: 683px; height: 539px; margin-left: 240px;"><tbody>
  <tr>
    <td width="100%" valign="top"><img vspace="0" hspace="0" border="0" src="../img/correo$@SLASH@$Caso4-grafico-EnvioMensaje.png" alt="Cliente gráfico. Envío de mensaje" title="Cliente gráfico. Envío de mensaje" style="width: 679px; height: 528px;" /><br />
    </td>
  </tr></tbody>
</table><br />
<ul>
  <ul>
    <ul>
      <ul>
        <ul>
          <ul>
            <li style="text-align: left;">
              <p style="margin-bottom: 0cm;" class="western"><style type="text/css"></style><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"></span></span></span></span><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"><span style="font-weight: bold;">Servidor Avatar</span>: lista de mensajes recibidos.</span></span></span></span></span></font></font></font></font></p></li>
            <ul>
              <li style="text-align: left;">
                <p><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"></span></span></span></span></span></font></font></font></font><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">Observamos como tenemos el mensaje anterior envíado desde línea de comandos y este último haciendo uso de Evolution. La siguiente figura muestra la parte final del buzón del usuario &quot;alumno&quot; (/var/mail/alumno).</span></span></span></span></span></font></font></font></font></p></li>
            </ul>
          </ul>
        </ul>
      </ul>
    </ul>
  </ul>
</ul>
<div style="margin-left: 40px;">
  <div style="margin-left: 240px;"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">
    <table border="1" style="width: 606px; height: 222px;"><tbody>
      <tr>
        <td width="100%" valign="top"><img width="600" vspace="0" hspace="0" height="212" border="0" title="Envío del cliente. Buzón" alt="Envío del cliente. Buzón" src="../img/correo$@SLASH@$caso4-servidor.jpg" />
        </td>
      </tr></tbody>
    </table></span></span></span></span></span></font></font></font></font></div><br /><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"></span></span></span></span></span></font></font></font></font></div><br /><br /><br /><hr style="width: 100%; height: 2px;" /><br />
<ul style="text-align: left;">
  <li> <span style="font-weight: bold;"> </span><font color="#0000ff" style="font-weight: bold;"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">Caso 5: </span></span></span></span></font></font></font></font><font color="#0000ff" style="font-weight: bold;"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"> envío de correo a usuarios de otros servidores en Internet usando Avatar como servidor de correo local</span></span></span></span></span></font></font></font></font></li>
  <ul>
    <li><font color="#0000ff" style="font-weight: bold;"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"></span></span></span></span></span></font></font></font></font><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">Este caso es idéntico al caso 3. <br /></span></span></span></span></span></font></font></font></font></li>
  </ul>
</ul><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"></span></span></span></span></span></font></font></font></font>
<ul style="text-align: left;">
  <ul>
    <li><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">¿Piensas que tienes qué modificar la configuración de Postfix? Pues en principio no, puedes usar la configuración explicada anteriormente, añadiendo los dominios a los que quieres enviar correo con de la directiva relay-domains. Así si quieres enviar correo a un usuario del dominio juntadeandalucia.es debes indicarlo en esta directiva.</span></span></span></span></span></font></font></font></font></li>
    <ul>
      <li value="1"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"></span></span></span></span></span></font></font></font></font><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">relay-domains = juntadeandalucia.es</span></span></span></span></span></font></font></font></font></li>
    </ul>
  </ul>
</ul><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"></span></span></span></span></span></font></font></font></font><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"></span></span></span></span></span></font></font></font></font>
<ul style="text-align: center;">
  <ul style="text-align: left;">
    <li value="1"><font size="2" style="font-family: trebuchet ms,verdana,arial,helvetica,sans-serif;">Prueba a hacer envíos de correos a usuarios de otros dominios en Internet tanto en modo telnet como con Evolution.</font><br /><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;"></span></span></span></span></span></font></font></font></font></li>
    <li value="1"><font color="#0000ff"><font color="#000000"><font face="Times New Roman, serif"><font size="2"><span lang="es-ES"><span style="font-style: normal;"><span style="text-decoration: none;"><span><span style="background: transparent none repeat scroll 0% 0%; -moz-background-clip: -moz-initial; -moz-background-origin: -moz-initial; -moz-background-inline-policy: -moz-initial;">No olvides que puedes tener problemas de envío si tu IP es dinámica. Puedes comprobarlo en el fichero de log (/var/log/alumno). Solucionaremos este asunto en el siguiente apartado. </span></span></span></span></span></font></font></font></font></li>
  </ul>
</ul><br />
