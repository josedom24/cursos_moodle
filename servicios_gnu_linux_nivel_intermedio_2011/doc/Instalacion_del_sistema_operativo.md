# Instalación del sistema operativo
<div style="text-align: justify;"> El sistema operativo que vamos a utilizar en nuestro servidor avatar es Debian GNU/Linux 5.0 (Lenny). Te ponemos algunos enlaces que te pueden ser de ayuda en la instalación:<br /> </div>
<ul>
  <li style="text-align: justify;"><a href="http://www.debian.org/index.es.html">http://www.debian.org/index.es.html</a>: Página oficial de esta distribución.<br /></li>
  <li style="text-align: justify;"><a href="http://www.debian.org/releases/lenny/debian-installer/index.en.html">http://www.debian.org/releases/lenny/debian-installer/index.en.html</a>: Página de descarga de la última versión de Debian 5.0 (5.0.8)<br /></li>
  <li style="text-align: justify;"><a href="http://www.debian.org/releases/lenny/installmanual">http://www.debian.org/releases/lenny/installmanual</a> :Guía de instalación oficial de Debian</li>
  <li style="text-align: justify;"><a id="post-786" class="title" href="http://www.dipler.org/2009/02/instalacion-de-debian-lenny-50/" rel="bookmark" title="Instalación de Debian Lenny 5.0">Instalación de Debian Lenny 5.0</a>: Un tutorial sobre la instalación del sistema operativo.</li>
</ul>
<div style="text-align: left;">Si dispones de conexión a Internet durante la instalación de avatar, recomendamos que te descargues el <a href="http://cdimage.debian.org/cdimage/archive/5.0.8/i386/iso-cd/debian-508-i386-netinst.iso">CD de instalación por red </a>que ocupa menos de 200 MB. Si decides descargar los CD completos, ten en cuenta que sólo necesitarás el primero, que nadie piense en descargarse los 31 CDs o los 5 DVDs oficiales :-), eso sólo sería necesario (y con matices) en un equipo que no pudiese conectarse nunca a Internet.<br /></div><br />
<div style="text-align: justify;">
  <table width="100%" border="1" style="text-align: left; margin-left: 0px; margin-right: 0px;"><tbody>
    <tr>
      <td width="100%" valign="top">IMPORTANTE: No es necesario que se instale el servidor gráfico en nuestro sistema operativo. Es más, no se recomienda hacerlo ya que el servidor lo vamos a administrar por línea de comandos y en muchas ocasiones incluso la administración se hará remotamente (los servidores no suelen tener un monitor conectado).
      </td>
    </tr></tbody>
  </table><br /><span style="font-weight: bold;">Nota sobre la versión de Debian</span>: Aunque actualmente la versión estable de Debian es la 6.0 o squeeze (desde el pasado 6 de Febrero), en este curso hemos optado por seguir utilizando la versión 5.0.7 o lenny por una razón principalmente: La versión de openldap de debian squeeze (2.4.23) incluye importantes modificaciones en la configuración que añaden más complejidad al tema de cuentas centralizadas, que es con diferencia el tema más difícil del curso. Para el resto de temas no debe haber importantes diferencias en la versión de Debian utilizada e incluso de Ubuntu, pero la versión utilizada en la toda la documentación y que se recomienda para realizar el curso es Debian lenny.<br /><br />Documentación sobre la distribución Debian:<br />
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
