# Trabajar con ficheros comprimidos

<h1 class="firstHeading">Trabajar con ficheros comprimidos <br />
</h1>

	  
<div id="bodyContent">
	    <h3 id="siteSub"><br />
</h3>
	    
	    

	    
	    <!-- start content -->
	    <table border="0" id="toc"><tbody><tr id="toctitle"><td align="center">
<b /><span class="toctoggle"><br />
</span>
</td></tr><tr id="tocinside"><td>
<div class="tocline"><a href="#Introducci.C3.B3n">1 Introducción</a><br /></div>
<div class="tocline"><a href="#Empaquetados_y_compresi.C3.B3n">2 Empaquetados y compresión</a><br /></div>
<div class="tocline"><a href="#Tipos">3 Tipos</a><br />
   <a href="#Zip">3.1 Zip</a>    <br />
   <a href="#TAR">3.2 TAR</a>    <br />
   <a href="#Gzip">3.3 Gzip</a><br />
   <a href="#Bzip2">3.4 Bzip2</a><br />
   <a href="#RAR">3.5 RAR</a><br />
   <a href="#ACE">3.6 ACE</a><br />

</div>
<div class="tocindent">
</div>
<div class="tocline"><a href="#Programas">4 Programas</a><br /></div>
<div class="tocline"><a href="#Descompresi.C3.B3n_de_un_fichero">5 Descompresión de un fichero</a><br /></div>
<div class="tocline"><a href="#Descompresi.C3.B3n_r.C3.A1pida_en_Gnome">6 Descompresión rápida en Gnome</a><br />
    <a href="#Explicaci.C3.B3n_Animada">6.1 Explicación Animada</a><br />

</div>
<div class="tocindent"><div class="tocindent">
</div>
</div>
<div class="tocline"><a href="#Creaci.C3.B3n_de_un_fichero_comprimido">7 Creación de un fichero comprimido</a><br /></div>
<div class="tocline"><a href="#Otros_tipos_de_compresi.C3.B3n">8 Otros tipos de compresión</a><br /></div>

</td></tr></tbody></table>
<a name="Introducci.C3.B3n"></a><h2> Introducción </h2>
<p style="text-align: justify;">La compresión de archivos es un recurso muy utilizado en el mundo de
la informática. A grandes rasgos, la compresión consiste en crear un
archivo de menor tamaño partiendo de uno o varios ficheros.
</p><p style="text-align: justify;">Las ventajas de la compresión son indudables ya que permiten un
mejor aprovechamiento de los soportes de datos como disquetes, CD-ROM,
etc. Habitualmente cuando descargamos algún fichero de Internet, éste
se encuentra comprimido para disminuir el tiempo necesario para
recibirlo. Por lo tanto, antes de poder utilizarlo, será necesario
descomprimirlo para devolverlo a su estado original.
</p><p style="text-align: justify;">En este documento vamos a ver los formatos de compresión más habituales y los procedimientos para trabajar con ellos.
</p><div style="text-align: justify;">
<a name="Empaquetados_y_compresi.C3.B3n"></a></div><h2 style="text-align: justify;"> Empaquetados y compresión </h2><div style="text-align: justify;">
</div><p style="text-align: justify;">Habitualmente lo que se conoce como compresión de un fichero
comprende dos pasos diferenciados: el empaquetado y la compresión
propiamente dicha.
</p><p style="text-align: justify;">Se conoce como empaquetado al proceso de crear un único fichero
partiendo de un conjunto de archivos. El fichero empaquetado es del
mismo tamaño que la suma de los archivos que contiene.La compresión
consiste en crear un archivo de menor tamaño a partir de otro.
</p><p style="text-align: justify;">Es muy común que el empaquetado y la compresión se realicen de
forma conjunta pero en algunas ocasiones no es la mejor opción. Cuando
estemos tratando con ficheros previamente comprimidos como pueden ser
canciones en formato MP3/OGG, imágenes JPG o vídeos no es una buena
idea volver a comprimirlos porque, en la mayoría de los casos, no se
obtiene ninguna mejora. En estas ocasiones, es más interesante
únicamente empaquetar los ficheros porque es un proceso mucho más
rápido que la compresión.
</p><div style="text-align: justify;">
<a name="Tipos"></a></div><h2 style="text-align: justify;"> Tipos </h2><div style="text-align: justify;">
</div><p style="text-align: justify;">Existen varios formatos de compresión pero el funcionamiento de todos es muy similar.
</p><div style="text-align: justify;">
<a name="Zip"></a></div><h3 style="text-align: justify;"> Zip </h3><div style="text-align: justify;">
</div><p style="text-align: justify;">El formato zip es el más utilizado en el mundo de la informática.
Una de las características más interesantes de este formato es que se
puede leer fácilmente en cualquier sistema. Por ello, es una buena
opción si queremos intercambiar ficheros entre Windows y Linux.
</p><div style="text-align: justify;">
<a name="TAR"></a></div><h3 style="text-align: justify;"> TAR </h3><div style="text-align: justify;">
</div><p style="text-align: justify;">El formato tar es únicamente de empaquetado, no de compresión. La
aplicación para trabajar con este formato se denomina 'tar'. De la
misma manera se llaman los ficheros que genera.
</p><div style="text-align: justify;">
<a name="Gzip"></a></div><h3 style="text-align: justify;"> Gzip </h3><div style="text-align: justify;">
</div><p style="text-align: justify;">En el mundo UNIX es muy habitual combinar varios programas sencillos
para realizar una tarea más compleja. Como acabamos de ver, un fichero
'tar' es un archivo que contiene otros muchos pero que no está
comprimido. El complemento a la utilidad 'tar' es el programa 'gzip'.
Esta aplicación nos permite comprimir un fichero. La combinación de los
dos programas, nos permite pasar de un conjunto de fichero a un archivo
comprimido que los contiene a todos.
Los ficheros empaquetados con 'tar' y comprimidos con 'gzip' suelen
tener un nombre de la forma 'nombre_fichero.tar.gz' pero en algunas
ocasiones se denominan como 'nombre_fichero.tgz'.
</p><div style="text-align: justify;">
<a name="Bzip2"></a></div><h3 style="text-align: justify;"> Bzip2 </h3><div style="text-align: justify;">
</div><p style="text-align: justify;">La utilidad Bzip2 es similar en comportamiento a Gzip pero aporta
una compresión más eficiente. De la misma forma que Gzip, Bzip2 se
suele utilizar en conjunción con 'tar'.
Los ficheros comprimidos con Bzip2 suelen tener la extensión '.bz2',
por lo tanto, si lo utilizamos junto con 'tar' obtendremos un fichero
de la forma 'nombre_fichero.tar.bz2'.
</p><div style="text-align: justify;">
<a name="RAR"></a></div><h3 style="text-align: justify;"> RAR </h3><div style="text-align: justify;">
</div><p style="text-align: justify;">El formato RAR es muy utilizado en sistemas Windows pero también es
posible trabajar con él en Linux. Al contrario de los formatos
nombrados hasta ahora, las especificaciones de RAR no son libres y
dependen de una única empresa. Por este motivo, no es un formato
recomendable si queremos facilitar el difusión de los archivos que
creemos.
</p><div style="text-align: justify;">
<a name="ACE"></a></div><h3 style="text-align: justify;"> ACE </h3><div style="text-align: justify;">
</div><p style="text-align: justify;">Al igual que RAR, el formato ACE es propietario y no es recomendable
utilizarlo para crear nuevos archivos. El soporte en Linux es muy
limitado y únicamente es posible descomprimir archivos ya creados.
</p><div style="text-align: justify;">
<a name="Programas"></a></div><h2 style="text-align: justify;"> Programas </h2><div style="text-align: justify;">
</div><p style="text-align: justify;">Habitualmente los programas para trabajar con archivos comprimidos
funcionan desde el terminal. Esto dificulta bastante su uso porque cada
uno de ellos admite un conjunto de opciones distintas. Para facilitar
la tarea, en Guadalinex se ha incluido la aplicación <em><strong>File Roller</strong></em>
que permite trabajar de forma homogénea con los distintos formatos de
ficheros comprimidos y además de forma gráfica e intuitiva desde el
escritorio.
</p><p style="text-align: justify;">En Guadalinex V3, la aplicación <em><strong>File Roller</strong></em> se puede encontrar en el menú <em><strong>Aplicaciones/Accesorios/Gestor de archivos comprimidos (File-roller)</strong></em>.
</p><div style="text-align: justify;">
<a name="Descompresi.C3.B3n_de_un_fichero"></a></div><h2 style="text-align: justify;"> Descompresión de un fichero </h2><div style="text-align: justify;">
</div><ul style="text-align: justify;"><li> Para descomprimir un fichero existente seleccionaremos la opción <em><strong>Abrir</strong></em>.
</li><li> En la ventana que se nos muestra debemos seleccionar el fichero que queremos descomprimir.
</li><li> Saldremos de la ventana pulsando el botón <em><strong>Abrir</strong></em>. 
</li><li> La aplicación nos mostrará el contenido del archivo comprimido.
</li><li> Para extraer todo el contenido seleccionaremos la opción &quot;Extraer&quot;. 
</li><li> En la siguiente ventana indicaremos dónde queremos guardar el contenido y pulsaremos el botón &quot;Extraer&quot;.
</li></ul><div style="text-align: justify;">
<a name="Descompresi.C3.B3n_r.C3.A1pida_en_Gnome"></a></div><h2 style="text-align: justify;"> Descompresión rápida en Gnome</h2><div style="text-align: justify;">
</div><p style="text-align: justify;">En guadalinex podemos optar por un sistema de descompresión más simple aún que el anterior.
</p><div style="text-align: justify;">
</div><ul style="text-align: justify;"><li> Simplemente bien en el escritorio y bien en el navegador de archivos <em><strong>Nautilus</strong></em>, nos colocamos encima de un archivo comprimido y pulsamos el botón derecho del ratón.
</li><li> Del menú contextual que aparece, elegimos la opción <em><strong>Extraer aquí</strong></em>.
</li><li> El contenido del fichero se descomprimirá en la carpeta actual inmediatamente.
</li></ul><div style="text-align: justify;">
<a name="Explicaci.C3.B3n_Animada"></a></div><h4 style="text-align: justify;"> Explicación Animada </h4><div style="text-align: justify;">
</div><p style="text-align: justify;"><a title="http://www.guadalinex.org/guadapedia/images/c/c0/Fileroller.gif" class="external" href="http://www.guadalinex.org/guadapedia/images/c/c0/Fileroller.gif"><img alt="Thumb-fileroller.gif" src="http://www.guadalinex.org/guadapedia/images/3/35/Thumb-fileroller.gif" /></a><span class="urlexpansion"> (<i>http://www.guadalinex.org/guadapedia/images/c/c0/Fileroller.gif</i>)</span> Pincha en la imagen para ver la animación a su tamaño completo.
</p><div style="text-align: justify;">
<a name="Creaci.C3.B3n_de_un_fichero_comprimido"></a></div><h2 style="text-align: justify;"> Creación de un fichero comprimido </h2><div style="text-align: justify;">
</div><p style="text-align: justify;">La creación de un fichero comprimido consta de dos pasos. En un
principio se crea un archivo vacío y posteriormente se le añade el
contenido.
</p><div style="text-align: justify;">
</div><ul style="text-align: justify;"><li> Para crear un fichero comprimido seleccionaremos la opción <em><strong>Nuevo</strong></em>.
</li><li> Indicaremos el nombre del archivo a crear y la carpeta donde se guardará.
</li><li> La opción <em><strong>Tipo de archivador</strong></em> se puede dejar en <em><strong>Automático</strong></em>
si al nombre del fichero le hemos añadido la extensión estándar para el
tipo de fichero deseado. Si no hemos utilizado una extensión, debemos
seleccionar explícitamente el tipo de archivo que deseamos crear. </li><li> Saldremos de la ventana pulsando sobre el botón <em><strong>Nuevo</strong></em>. Con esto se habrá creado el archivo vacío.
</li></ul><div style="text-align: justify;">
</div><p style="text-align: justify;"><br />
A continuación debemos añadir contenido al fichero recién creado.
</p><div style="text-align: justify;">
</div><ul style="text-align: justify;"><li> Para ello seleccionaremos la opción <em><strong>Añadir</strong></em> y escogeremos los archivos que deseamos agregar.
</li><li> Veremos cómo los ficheros seleccionados se han añadido al contenido del archivo comprimido.
</li><li> Para finalizar el proceso seleccionaremos la opción <em><strong>Cerrar</strong></em> o saldremos del programa.
</li></ul><div style="text-align: justify;">
<a name="Otros_tipos_de_compresi.C3.B3n"></a></div><h2 style="text-align: justify;"> Otros tipos de compresión </h2><div style="text-align: justify;">
</div><p style="text-align: justify;">Todos los programas que hemos visto utilizan la conocida como
&quot;compresión sin pérdida&quot;. Este tipo de compresión permite reconstruir
de forma exacta el contenido de los ficheros originales partiendo de un
archivo comprimido.
</p><p style="text-align: justify;">Existe otra modalidad de compresión denominada &quot;compresión con
pérdida&quot;. Utilizando esta tecnología no es posible reconstruir de forma
exacta el fichero original si se parte de un comprimido porque en el
proceso de compresión se ha perdido información. La compresión con
pérdida se utiliza extensivamente en formatos gráficos, sonido y vídeo
donde es admisible una pequeña reducción en la calidad a cambio de una
disminución significativa del tamaño.
</p><p style="text-align: justify;">Todos los formatos habituales como JPG, MP3, Ogg, MPEG, etc.
utilizan compresión con pérdida y al resultado obtenido le aplican una
compresión sin pérdida como la que hemos visto en este documento. Por
lo tanto, si intentamos comprimir algunos de estos formatos que ya se
encuentran comprimidos no obtendremos ninguna mejora significativa y,
en algunas ocasiones, el fichero resultante puede ser de mayor tamaño
que el original.</p><p style="text-align: justify;"><font size="1">Referencia:</font></p><p style="text-align: justify;"><font size="1">Recetas Guadalinex v3 (http://www.guadalinex.org/guadapedia/index.php/Receta:_Trabajar_con_archivos_comprimidos_%28Guadalinex_V3%29)<br /></font></p><p style="text-align: justify;"><font size="1">Este documento se distribuye bajo una licencia Creative Commons Reconocimiento-NoComercial-CompartirIgual<br />
<br />Reconocimiento. Debe reconocer los créditos de la obra de la manera especificada por el autor o el licenciador.<br />No comercial. No puede utilizar esta obra para fines comerciales.<br />Compartir bajo la misma licencia. Si altera o transforma esta obra, o
genera una obra derivada, sólo puede distribuir la obra generada bajo
una licencia idéntica a ésta.<br />
<br />
<br />
Para más información visitar: http://creativecommons.org/licenses/by-nc-sa/2.5/es/</font>

</p>
<p style="margin-bottom: 0cm;"><br />

</p>
<p style="text-align: justify;">
</p>
<a name="M.C3.A1s_Informaci.C3.B3n"></a></div>
