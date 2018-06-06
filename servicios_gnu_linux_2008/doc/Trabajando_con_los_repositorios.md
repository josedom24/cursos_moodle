# Trabajando con los repositorios
<h2> ¿Qué son los repositorios?</h2>
<div style="text-align: left;">El repositorio es a todos los efectos un archivo ordenado donde son almacenados los paquetes Debian (sean estos paquetes binarios o fuentes) en un modo bien organizado, con una estructura bien definida y constantemente actualizados.<br />
  <p>Los paquetes contenidos en un repositorio son indexados en estos archivos:</p>
  <p><em>Packages.gz</em> (son paquetes que contienen los binarios).<br /> <em>Sources.gz</em> (son aquellos que contienen los fuente).</p>En cada sistema Debian, los repositorios utilizados vienen indicados en el archivo <em>/etc/apt/sources.list</em>.<br /><br />Para actualizar la lista de paquetes en nuestro ordenador utilizamos la instrucción:<br /><pre># apt-get update</pre>
  <h2>Estrcutura del fichero /etc/apt/source.list</h2>Vamos a editar el fichero source.list<br /><pre># cd /etc/apt
# nano sources.list</pre>Veamos un ejemplo de un posble contenido:<br /><pre>#deb cdrom:[Debian GNU/Linux 4.0 r4a _Etch_ - Official i386 CD Binary-1 20080803-21:07]/ etch contrib main
#deb cdrom:[Debian GNU/Linux 4.0 r4a _Etch_ - Official i386 CD Binary-1 20080803-21:07]/ etch contrib main

deb http://ftp.es.debian.org/debian/ etch main contrib non-free
deb-src http://ftp.es.debian.org/debian/ etch main contrib non-free

deb http://security.debian.org/ etch/updates main contrib
deb-src http://security.debian.org/ etch/updates main contrib</pre>Cada línea que describe un repositorio tiene una sintaxis predeterminada que podemos resumir en:
  <p><code>deb uri distribution [component...]</code></p>
  <p>Analizamos los componentes por separado, así lo entendemos mejor:</p>
  <ul>
    <li><strong>deb o deb-src</strong> sirve para indicar si el repositorio indicado contiene paquetes binarios o paquetes fuente (si tiene ambos es necesario especificarlo en dos lineas diferentes).</li>
  </ul>
  <ul>
    <li><strong>uri</strong> indica la dirección donde es posible encontrar el repositorio, y además podemos elegir entre los siguientes métodos de acceso a los paquetes:</li>
    <ul>
      <li><strong>cdrom</strong> permite acceder a un repositorio presente en un cdrom.</li>
      <li><strong>http</strong>: permite acceder tramite el protocolo <em>http.</em></li>
      <li><strong>ftp</strong> permite acceder a un repositorio tramite el protocolo ftp.</li>
      <li>file,rsh, copy son otras opciones menos usadas</li>
    </ul>
    <li>
      <p><strong>distribution</strong> indica la distribución (o rama) utilizada, es posible usar el nombre en código (sarge, etch, lenny, ...) o el nombre genérico (stable, testing, unstable)</p></li>
  </ul>
  <div style="margin-left: 40px;"> Cuando un repositorio apunta a una de las ramas (oldstable, stable, testing), apuntan a las versiones de turno, que en este momento son:
    <p>Oldstable --&gt; sarge<br /> stable --&gt; etch<br /> testing --&gt; lenny</p>
    <p>Cada vez que se libera una nueva versión de Debian, se actualizan los enlaces para que apunten a los nuevos nombres-clave, por ejemplo, cuando se libere lenny, oldstable apuntará a etch, stable será lenny y testing será el nombre de toy-story que siga.</p> </div>
  <ul>
    <li>
      <p><strong>component</strong> indica las secciones del repositorio, <em>non-free , main , contrib...</em></p></li>
    <ul>
      <li>
        <p><strong>main</strong> es la sección principal, que contiene el 90% de los paquetes presentes en nuestra Debian.</p></li>
      <li>
        <p><strong>contrib</strong> encontramos los paquetes que cumplen con 5 ó 6 puntos de las DFSG (Debian Free Software Guidelines), pero que dependen de paquetes que no la respetan.<br /> (DFSG = lineamientos o requisitos que una licencia debe cumplir para que sea definida como <em>libre</em> segun el proyecto Debian <a rel="nofollow" title="http://www.debian.org/social_contract#guidelines" href="http://www.debian.org/social_contract#guidelines">http://www.debian.org/social_contract#guidelines</a>).<br /></p></li>
      <li>
        <p><strong>non-free</strong> contiene los paquetes que poseen limitaciones en su distribución (como por ejemplo aquellos que no pueden ser usados en ámbito comercial o porque dependen de paquetes que no respetan las DFSG).</p></li>
    </ul>
  </ul>
  <table width="100%" border="1"><tbody>
    <tr>
      <td width="100%" valign="top"><br />1) Edita el fichero de configuración de APT de tu máquina y comprueba en que rama de Debian estamos trabajando y que repositorios estamos usando.<br /><br />
      </td>
    </tr></tbody>
  </table><br />
  <h2>Añadiendo un nuevo repositorio</h2>Podemos añadir a nuestra lista repositorios no oficiales. Por ejemplo el <a href="http://www.esdebian.org/foro/24349/nuevo-mirror-debian-multimedia">repositorio de multimedia</a>, para ello debemos añadir a nuestro fichero /etc/apt/sources.list la siguiente línea:<br /><br /><code>deb http://www.debian-multimedia.org stable main<br /><br /></code>Y a continuación actualizamos nuestra lista de paquetes usuando:<br /><pre># apt-get update</pre>
  <h2>
    <table width="100%" border="1"><tbody>
      <tr>
        <td width="100%" valign="top"><br />1) Incluye en el repositorio de multimedia y actualiza la lista de paquetes.<br /><br />
        </td>
      </tr></tbody>
    </table><br /></h2>
  <h2>Firmas de los repositorios</h2>
  <p>Cuando instalas paquetes binarios desde Internet tu sistema puede quedar comprometido si los descargas de sitios poco fiables. Incluso utilizando sitios oficiales puede ser un grave problema de seguridad si alguien consigue hacerse pasar por el servidor o introduce paquetes maliciosamente modificados.</p>
  <p>Para evitar todo esto, los repositorios disponen de una firma PGP que garantiza la autenticidad de sus paquetes. <code>APT</code> comprueba que los paquetes vienen firmados por quien dice ser, accediendo en un servidor público de claves.</p>Al ejecutar el último update hemos obtenido el siguiente mensaje:<br /><pre>W: GPG error: http://www.debian-multimedia.org stable Release: Las firmas siguientes no se pudieron verificar porque
su llave pública no está disponible: NO_PUBKEY 07DC563D1F41B907</pre>A pesar de estos avisos, se pueden instalar paquetes como siempre, pero no habrá ninguna garantía de su autenticidad. El programa <code>apt-get</code> suele pedir una confirmación de este tipo cuando se instalan paquetes cuya autenticidad no se puede comprobar:<br /><br /><pre class="console">AVISO: ¡No se han podido autenticar los siguientes paquetes!
 xxxxxxxxxxxxxxxx
¿Instalar estos paquetes sin verificación [s/N]?

</pre>Para solucionar este problema sigue los siguientes pasos:<br /><br />
  <table width="100%" border="1"><tbody>
    <tr>
      <td width="100%" valign="top"><br />1) Instala el paquete gnupg, si no esta instalado.<br /><br />2) Ejecuta el programa <code>gpg</code> como root. De ese modo se crean el directorio <code>.gnupg</code> y los ficheros de configuración por defecto. Pulsa C-c cuando haya arrancado.<br /><br />3) Ahora edita el fichero <code>/root/.gnupg/gpg.conf</code> y añade (o descomenta) esta línea:<br /><pre>keyserver-options auto-key-retrieve
</pre>Para crear la clave pública correspondiente a la firma (que es el numero que sale al final: 07DC563D1F41B907) debemos ejecutar la siguiente instrucción:<br /><pre>gpg --keyserver subkeys.pgp.net --recv-keys 07DC563D1F41B907
gpg: solicitando clave 1F41B907 de hkp servidor subkeys.pgp.net
gpg: clave 1F41B907: “Christian Marillat “ sin cambios
gpg: Cantidad total procesada: 1
gpg: sin cambios: 1</pre> Y la puedes incorporar al anillo de claves de <strong>APT</strong> con este otro comando. Igual que antes, puede que tengas que ejecutarlo varias veces hasta que diga algo como esto:<br /><pre>gpg --export --armor 07DC563D1F41B907 | apt-key add -- OK</pre>Y para terminar, un <code>apt-get update</code> que debería salir sin esos feos avisos, y con total garantía de autenticidad sobre lo que instalas. Evidentemente, se supone que tú, como administrador, deberías contrastar que esa firma corresponde a alguien “fiable”.<br /><br /><span style="font-weight: bold;">Otra alternativa (no disponible en todos los repositorios):<br /></span>Instalar un paquete keyring del repositorio que hemos intalado, en nuestro caso:<br /><pre>apt-get install debian-multimedia-keyring</pre>
      </td>
    </tr></tbody>
  </table><br /><br /><pre> </pre><pre><span style="font-weight: bold;"></span></pre> </div>
