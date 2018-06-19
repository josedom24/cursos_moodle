# 3.- Instalación del sistema operativo
<div style="text-align: justify;"> El sistema operativo que vamos a utilizar en nuestro servidor avatar es Debian GNU/Linux 5.0 (Lenny). Lo próximo que tenemos que hacer es la instalación del sistema operativo en el servidor, para ello deberás descargarte una imagen ISO del instalador y realizar la instalación en el equipo que hayas elegido para que sea avatar. Te ponemos algunos enlaces que te pueden ser de ayuda en la instalación:<br /> </div>
<ul>
  <li style="text-align: justify;"><a href="http://www.debian.org/index.es.html">http://www.debian.org/index.es.html</a>: Página oficial de esta distribución.<br /></li>
  <li style="text-align: justify;"><a href="http://www.debian.org/CD/http-ftp/">http://www.debian.org/CD/http-ftp/</a>: Página de descarga de la última versión de Debian.</li>
  <li style="text-align: justify;"><a href="http://www.debian.org/releases/stable/i386/index.html.es">http://www.debian.org/releases/stable/i386/index.html.es</a> :Guía de instalación oficial de Debian</li>
  <li style="text-align: justify;"><a title="Instalación de Debian Lenny 5.0" rel="bookmark" href="http://www.dipler.org/2009/02/instalacion-de-debian-lenny-50/" class="title" id="post-786">Instalación de Debian Lenny 5.0</a>: Un tutorial sobre la instalación del sistema operativo.</li>
</ul>
<div style="text-align: left;">Si dispones de conexión a Internet durante la instalación de avatar, recomendamos que te descargues el <a href="http://cdimage.debian.org/debian-cd/5.0.4/i386/iso-cd/debian-504-i386-netinst.iso">CD de instalación por red </a>que ocupa menos de 200 MB. Si decides descargar los CD completos, ten en cuenta que sólo necesitarás el primero, que nadie piense en descargarse los 31 CDs o los 5 DVDs oficiales :-), eso sólo sería necesario (y con matices) en un equipo que no pudiese conectarse nunca a Internet.<br /></div><br />
<div style="text-align: justify;">
  <table border="1" width="100%" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
    <tr>
      <td width="100%" valign="top">IMPORTANTE: No es necesario que se instale el servidor gráfico en nuestro sistema operativo. Es más, no se recomienda hacerlo ya que el servidor lo vamos a administrar por línea de comandos y en muchas ocasiones incluso la administración se hará remotamente (los servidores no suelen tener un monitor conectado).
      </td>
    </tr></tbody>
  </table><br />Documentación sobre la distribución Debian:<br />
  <ul>
    <li><span style="font-weight: bold;">Instalación de programas</span>: Cuando instalamos un programa o servicio, el software esta empaquetado en formato deb, que además es la extensión de los ficheros de paquetes de software de Debian y derivadas (p ej. Ubuntu). El programa predeterminado para manejar estos paquetes es dpkg, generalmente vía apt/aptitude aunque hay interfaces gráficas como Synaptic, PackageKit o Gdebi que simplifican el trabajo.</li>
  </ul>
  <ul>
    <ul>
      <li><a href="http://wiki.debian.org/AptCLI">Tutorial de apt en Debian Wiki</a></li>
      <li><a href="http://wiki.debian.org/Aptitude">Tutorial de aptitude en Debian Wiki</a></li>
      <li><a href="http://www.josedomingo.org/web/mod/page/view.php?id=1861"><span>Manejar paquetes en Debian</span></a></li>
      <li><span><a href="http://preguntaslinux.org/-howto-apt-y-aptitude-t-5780.html">Uso básico de apt/aptitude</a></span></li>
    </ul>
  </ul>
  <ul>
    <li><span style="font-weight: bold;">Procesos y niveles de ejecución:</span> La más simple definición de un proceso podría ser que es una instancia de un programa en ejecución (corriendo). Los niveles de ejecución determinan que procesos se ejecutan en el arranque del sistema operativo.</li>
  </ul>
  <ul>
    <ul>
      <li><a href="http://www.linuxtotal.com.mx/index.php?cont=info_admon_012">Manual básico de administración de procesos</a></li>
      <li><a href="http://www.debian-administration.org/articles/212">An introducction to run-levels</a><br /></li>
    </ul>
  </ul>
  <ul>
    <li><span style="font-weight: bold;">Configuración de la red</span>: Una de las primeras tareas después de la instalación del sistema operativo es la configuración de la red.</li>
  </ul>
  <ul>
    <ul>
      <li><a href="http://www.guatewireless.org/os/linux/distros/debian/una-introduccion-a-configuracion-de-redes-en-debian/">Una introducción a la configuración de redes en Debian</a><br /></li>
    </ul>
  </ul><br /><hr style="width: 100%; height: 2px;" /><br /></div>
