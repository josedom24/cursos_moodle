# Niveles de ejecución. Arranque y parada de los servicios
<h1 style="text-align: justify;"> Niveles de ejecución. Arranque y parada de los servicios</h1>
<div style="text-align: justify;"> Los niveles de ejecución ( Run Levels ) definen diferentes estados de funcionamiento de un Sistema Linux.<br /><br />0 Parada del sistema<br /> 1 Modo monousuario<br /> 2 Modo multiusuario<br /> 3 Modo multiusuario<br /> 4 No usado<br /> 5 Modo multiusuario<br /> 6 Parada y arranque<br /> 7-9 No se usan<br /><br /></div>
<h2 style="text-align: justify;">Secuencia de arranque</h2>
<div style="text-align: justify;">1) Debian arranca ejecutando el programa init. El archivo de configuración de init es /etc/inittab.<br /><br />La entrada initdefault determina el nivel de ejecución inicial del sistema.<br /><br />
  <table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
    <tr>
      <td width="100%" valign="top"><br />1) Edita el fichero<span style="font-weight: bold;"> /etc/inittab</span>, localiza la entrada initdefault, y determina en que nivel de ejecución está trabajando el sistema.<br /><br />2) También puedes obtener el nivel de ejecución actual ejecutando la instrucción <span style="font-weight: bold;">runlevel</span>.<br /><br />
      </td>
    </tr></tbody>
  </table> <br />2) Los primeros scripts que se ejecutan a continuación (indicado en la linea del fichero /etc/inittab: <span style="font-weight: bold;">si::sysinit:/etc/init.d/rcS) </span>son los que se encuentra en el directorio<span style="font-weight: bold;"> /etc/rcS. </span>Estos scripts son los encargados de realizar algunas tareas como: <br /><br />
  <ul style="text-align: justify;">
    <li>Monta el file system root y /proc.</li>
    <li>Elimina temporales y archivos de bloqueo.</li>
    <li>Establece el reloj</li>
    <li>Inicia scripts de red y activa la partición swap.</li>
    <li> Activa el teclado y fuentes.</li>
    <li>Carga módulos.</li>
    <li>Establece valores a muchas variables del entorno:PATH, HOSTNAME,...</li>
    <li>Arranca la swap</li>
    <li>Arranca fsck automático, si hace falta.</li>
    <li>Activa quotas.</li>
    <li>Chequea los argumentos pasados al kernel.</li>
    <li>Chequea los filesystems</li>
    <li>Inicializa los puertos serie.</li>
    <li>Puertos USB.</li>
  </ul>
  <table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
    <tr>
      <td width="100%" valign="top"><br /> 1) Lista los ficheros que se encuentran en el directorio /etc/rcS.d<br /><br />2) Comprueba que son enlaces simbólicos a los scripts que se encuentran en el directorio /etc/init.d<br /><br />
      </td>
    </tr></tbody>
  </table> <br /><br /> 3) A continuación se ejecutan los scripts de inicialización de los servicios del nivel de ejecución por defecto. Estos scripts se encuentran en los directorios <span style="font-weight: bold;">/etc/rc<span style="font-style: italic;">n</span></span> donde <span style="font-style: italic;">n</span> es el nivel de ejecución.<br /><br />Ejemplo:<br /><br />Nivel Script Directorio<br /> 0 rc 0 /etc/rc0.d/<br /> 1 rc 1 /etc/rc1.d/<br /> 2 rc 2 /etc/rc2.d/<br /> 3 rc 3 /etc/rc3.d/<br /><br />Es el script <span style="font-weight: bold;">/etc/init.d/rc</span> el que procesa todos los archivos K y S de los directorios <span style="font-weight: bold;">/etc/rc<span style="font-style: italic;">n</span>.d </span> </div>
<ul style="text-align: justify;">
  <li>Para ( con el argumento stop ) aquellos procesos que comienzan por K ( kill )</li>
  <li>Lanza ( con el argumento start ) los que comienzan por S ( start ).</li>
  <li>Después de la letra S o K hay dos dígitos numéricos que indican el orden de ejecución. El orden es ASCII.</li>
  <li>Todos los ficheros K o S son enlaces simbólicos a los scrips de cada servicio que están en el directorio <span style="font-weight: bold;">/etc/init.d</span></li>
</ul>
<div style="text-align: justify;"> </div>
<div> </div>
<table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />1) Visualiza los ficheros de los distintos directorios <span style="font-weight: bold;">/etc/rc<span style="font-style: italic;">n</span>.d</span>.<br />2) Comprueba los ficheros de ejecución del nivel de ejecución que se ejecuta por defecto en Debian.<br />3) Con la instrucción <span style="font-weight: bold;">telinit</span> podemos ejecutar otrps niveles de ejecución. Entra en el nivel monousuario. Entra en el nivel de reinicio. Entra en el nivel de parada del sistema.<br />
    </td>
  </tr></tbody>
</table>
<div style="text-align: justify;"><br />De modo esquemático podemos ver:<br /><br /><img hspace="0" height="566" width="1110" vspace="0" border="0" src="../img/Pantallazo.png" alt="runlevels" title="runlevels" /><br /><br />4) ¿Qué hacer para eliminar un servicio en un determinado nivel?<br /> </div>
<ul style="text-align: justify;">
  <li>Borrar el vínculo simbólico en /etc/rcn.d/</li>
  <li>Renombrarlo con algo que no empiece con S o K y dejarlo por si queremos luego activarlo.</li>
  <li>Lo que no hay que hacer nunca es eliminar el archivo original en /etc/init.d/</li>
</ul>
<div style="text-align: justify;"> </div>
<table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />1) Vamos a eliminar el servicio ssh (encargado de iniciar el servidor gráfico) del nivel de ejecución 2, para ello elimina el fichero que inicia ese servicio.<br />2) Reinica el sistema y comprueba que el servidor gráfico no se ha iniciado.<br />3) Para restablecer el enlace simbólico para que podamos iniciar el servicio usamos la instrucción <span style="font-weight: bold;">update-rc.d</span> (busca la página del manual para aprender más sobre esta instrucción. Ejecuta:<br /><br /><span style="font-weight: bold;">update-rc.d gdm defaults </span>para crear los enlaces simbólicos que ejecutan el script de gdm<br />4) Vuelve a reiniciar el sistema y comprueba que el servidor gráfico se vuelve a ejecutar.<br />5) Pregunta: ¿Para qué podríamos utilizar la configuración de distintos niveles de ejecución?<br /><br />
    </td>
  </tr></tbody>
</table>
<div style="text-align: justify;"><br /> </div>
<h2 style="text-align: justify;">Arranque y parada de lo servicios</h2>
<div style="text-align: justify;">Una vez que se han cargado los servicios que se encuentran en el directorio /etc/rc2.d, podemos comprobar que los demonios correspondientes a cada servicio se están ejecutando con la instrucción:<br /><br /><pre># ps -A</pre><br />En cualquier momento podemos parar o reiniciar cualquier servicio ejecutando los scripts del directorio /etc/init.d con las siguientes opciones: start, stop, restart, force-reload,...<br /><br /><br /> </div>
<table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />1) Comprueba que el servicio ssh se está ejecutando.<br />2) Para el servicio, y comprueba con la instrucción ps que el proceso no se está ejecutando.<br />3) Vuelve a reiniciar el servicio.<br /><br />
    </td>
  </tr></tbody>
</table> <br />
<h2 style="text-align: justify;">Envío de señales a los procesos</h2>
<div style="text-align: justify;">Es posible el envío de distintas señales a los procesos. La más usada es matar un proceso, si por ejemplo se queda inactivo. Para ello utilizamos la siguiente instrucción:<br /><br /><pre>kill -9 <span style="font-style: italic;">PID</span></pre><br />El PID es el identificador del proceso, y lo puedes obtener mirando la lista de procesos por ejemplo con ps -A.<br /><br />Podemos también utilizar la siguiente instrucción<br /><br /><pre>killall <span style="font-style: italic;">nombredelproceso</span></pre><br />Del mismo modo puedes ver el nombre del proceso mirando la lista de procesos con ps.<br /><br /> </div>
<table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
  <tr>
    <td width="100%" valign="top"><br />1) Imagínate que el servidor gráfico se queda &quot;colgado&quot;. Entra en un terminal de texto con CTRL+ALT+F1, y tras iniciar sesión como root mata el proceso gdm (Gestor de arranque del servidor gráfico).<br /><br />2) Para comprobar que el servidor gráfico no funciona puedes hacer varias cosas: lista los procesos y comprueba que no existe el proceso gdm ni el Xorg. También puedes intentar entrar en la consola gráfica con CTRL+ALT+F7.<br /><br />3) Vuelve a ejecutar el gestor de arranque gráfico gdm.<br /><br />4) Del mismo modo puedes matar el demonio del servicio ssh, y volver a reiniciarlo posteriormente. <br /><br />
    </td>
  </tr></tbody>
</table><br />
