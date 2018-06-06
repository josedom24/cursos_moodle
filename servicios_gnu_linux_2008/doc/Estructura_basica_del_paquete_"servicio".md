# Estructura básica del paquete "servicio"
<div style="text-align: justify;"> Binarios propios: </div>
<ul style="text-align: justify;"> 
  <li>/usr/bin (/usr/sbin)</li> 
</ul>
<div style="text-align: justify;"> Bibliotecas propias: </div>
<ul style="text-align: justify;"> 
  <li>/usr/lib/servicio/</li> 
</ul>
<div style="text-align: justify;"> Ficheros configurables: </div>
<ul style="text-align: justify;"> 
  <li>/etc/servicio/: Directorio de ficheros de configuración</li> 
  <li>/etc/default/servicio: Opciones extra para el inicio o parada del demonio</li> 
</ul>
<div style="text-align: justify;"> Ficheros de funcionamiento: </div>
<ul style="text-align: justify;"> 
  <li>/var/log/servicio (/var/log/syslog): Registro de actividad</li> 
  <li>/var/lib/servicio: Datos modificados durante la ejecución </li> 
  <li>/var/run: PID y socket</li> 
  <li>/var/lock: Bloqueos<br /></li> 
</ul>
<div style="text-align: justify;"> Documentación: </div>
<ul style="text-align: justify;"> 
  <li>/usr/share/doc/servicio/: Información del paquete</li> 
  <li>/usr/share/man/: Páginas del manual </li> 
</ul>
<div style="text-align: justify;"> Otros: </div>
<ul style="text-align: justify;"> 
  <li>/etc/init.d/servicio: Script de manejo del demonio</li> 
</ul>
