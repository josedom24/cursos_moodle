# Configuración de un proxy APT con approx
<div style="text-align: justify;">Instala el paquete approx en mortadelo mediante: <pre>aptitude install approx</pre> Edita el fichero /etc/approx/approx.conf y define las réplicas http que quieres utilizar, por ejemplo: <pre>debian http://ftp.es.debian.org/debian
security http://security.debian.org/debian-security
</pre> Reinicia el demonio de approx. Edita el fichero /etc/apt/sources.list de mortadelo y deja las siguientes líneas: <pre>deb http://127.0.0.1:9999/debian lenny main contrib non-free
deb http://127.0.0.1:9999/security lenny/updates main contrib
</pre> Realiza una actualización del sistema con: <pre>aptitude update
aptitude full-upgrade</pre> Edita ahora el fichero /etc/apt/sources.list de filemon y deja las siguientes líneas: <pre>deb http://10.0.0.10:9999/debian lenny main contrib non-free
deb http://10.0.0.10:9999/security lenny/updates main contrib
</pre> Repite la actualización del sistema como en mortadelo y disfruta con la velocidad de descarga :-)</div>
