# Crear manualmente un usuario en UNIX
<div style="text-align: justify;">Con idea de comprender qué significa crear un usuario en UNIX, crearemos un usuario de forma manual siguiendo los siguientes pasos.<br /><br />Características del nuevo usuario:<br />
  <ul>
    <li>Nombre de usuario: felisa</li>
    <li>Nombre Completo: Felisa Gómez García<br /></li>
    <li>Contraseña: 123456</li>
    <li>Grupo principal: curso</li>
    <li>UID: 1010</li>
    <li>GID:1010</li>
    <li>Directorio home: /home/felisa</li>
    <li>Shell: /bin/bash<br /></li>
  </ul>
  <ol>
    <li>Creamos el grupo principal del usuario, añadiendo la siguiente línea al fichero /etc/group:</li> <pre>curso:x:1010:</pre>
    <li>Creamos el usuario (salvo su contraseña), añadiendo la siguiente línea al fichero /etc/passwd:</li> <pre>felisa:x:1010:1010:Felisa Gómez García,,,:/home/felisa:/bin/bash</pre>
    <li>Ciframos la contraseña con el algoritmo MD5 (instalamos previamente el paquete grub):</li> <pre>grub-md5-crypt
Password:
Retype password:</pre>
    <li>Incluimos la contraseña anterior en una línea del fichero /etc/shadow (por ejemplo):</li> <pre>felisa:$1$01dvo$eW1kagvwzOAoSLdTJyaoo0:13730:0:99999:7:::</pre>
    <li>Creamos el directorio home de felisa</li> <pre>mkdir /home/felisa</pre>
    <li>Copiamos el contenido del directorio /etc/skel</li> <pre>cp /etc/skel/.* /home/felisa</pre>
    <li>Cambiamos el usuario propietario y el grupo propietario del directorio home de felisa y de todos los ficheros que contiene:</li> <pre>chown -R 1010:1010 /home/felisa</pre>
    <li>Comprobamos que todo está bien haciendo un login en el sistema con el usuario felisa y listando el contenido de su directorio.</li>
  </ol></div>
