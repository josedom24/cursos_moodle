# Uso básico de APT
<h2 style="text-align: justify;"><span style="font-weight: bold;">Instalar paquetes</span>:<br /></h2>
<div style="text-align: justify;"> Vamos a instalar un servicio de ejemplo, utilizando la herramienta apt-get. El servicio que vamos a instalar es ntp, que nos permite la sincronización del reloj del sistema. <br /><br />Para ello vamos a utilizar la instrucción:<br /><pre>#apt-get install ntp</pre><pre>Leyendo lista de paquetes... Hecho
Creando árbol de dependencias
Leyendo la información de estado... Hecho
Paquetes sugeridos:
 ntp-doc
Se instalarán los siguientes paquetes NUEVOS:
 ntp
0 actualizados, 1 se instalarán, 0 para eliminar y 8 no actualizados.
Necesito descargar 434kB de archivos.
After this operation, 1065kB of additional disk space will be used.
Des:1 http://192.168.1.1 lenny/main ntp 1:4.2.4p4+dfsg-7 [434kB]
Descargados 434kB en 0s (5872kB/s)
Seleccionando el paquete ntp previamente no seleccionado.
(Leyendo la base de datos ...
112173 ficheros y directorios instalados actualmente.)
Desempaquetando ntp (de .../ntp_1%3a4.2.4p4+dfsg-7_i386.deb) ...
Processing triggers for man-db ...
Configurando ntp (1:4.2.4p4+dfsg-7) ...
Starting NTP server: ntpd.</pre>Veamos algunos conceptos antes de contestar:<br /> </div>
<ul style="text-align: justify;">
  <li>¿Qué son los paquetes extras? Son las depedencias, los paquetes necesarios para que funcione el paquete que queremos usar.</li>
  <li>¿Qué son los paquetes sugeridos? Son paquetes relacionados con el que queremos instalar y que ofrecen alguna funcionalidad extra.</li>
</ul>
<div style="text-align: justify;">La herramienta apt-get descarga de los repositorios los paquetes necesarios y utilizando dpkg los instala y configura. Una vez concluida la instalación el servicio ntp estará funcionando.<br /><br />
  <table width="100%" border="1"><tbody>
    <tr>
      <td width="100%" valign="top"><br />1) Instala ahora otro servidor que vamos a utilizar durante el curso: el SSH, que nos permite la conexión remota de forma segura a nuestro ordenador.<br /><br />
      </td>
    </tr></tbody>
  </table><br /> </div>
<h2 style="text-align: justify;"><span style="font-weight: bold;">Desinstalar paquetes</span>:</h2>
<div style="text-align: justify;"> La opción de apt-get que debemos usar para desisntalar nuestro paquete es la siguiente:<br /><pre># apt-get remove ntp</pre>Esta opción no elimina los ficheros de configuración del servicio, para hacerlo tenemos que usar la siguiente opción:<br /><pre># apt-get remove --purge ntp</pre> <span style="font-weight: bold;">Atención!!!: Cuando desinstalamos un paquete, ¿se desinstalan las dependencias?</span><br /><span style="font-weight: bold;"></span><br />
  <table width="100%" border="1"><tbody>
    <tr>
      <td width="100%" valign="top"><br />1) Desinstala el servidor SSH con apt-get remove. Comprueba que no se han borrado los ficheros de configuración.<br /><br />2) Vuelve instalarlo, y desinstala ahora utilizando la opción purge. Comprueba que todos los ficheros relacionados se han borrado.<br /><br />3) Vuelve a instalar el servidor SSH, ya que lo vamos a utilizar durante el curso. ¿Por qué a partir de la segunda instlación el proceso es más rápido?<br /><br />
      </td>
    </tr></tbody>
  </table><br /><span style="font-weight: bold;"></span><span style="font-weight: bold;"></span><br /><span style="font-weight: bold;"></span></div>
