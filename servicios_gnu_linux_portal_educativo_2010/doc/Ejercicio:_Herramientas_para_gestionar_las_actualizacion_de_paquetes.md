# Ejercicio: Herramientas para gestionar las actualización de paquetes
<div style="text-align: justify;">Las actualizaciones automáticas de los paquetes del sistema, o la notificación de los mismos, es una tarea importante que deben realiza los administradores de sistema. Lo que pretendemos con este ejercicio es aprender herramientas que nos permiten automatizar las tareas de actualización que puede ser mas que beneficioso, sobre todo por el ahorro de tiempo. <br /><br />
  <h1>Apticron</h1>Apticron es un pequeño script que se encarga de comprobar las actualizaciones del sistema, descargarlas (pero no instalarlas), generar un informe y enviarlo por correo al administrador.<br /><br />
  <table border="1" width="100%"><tbody>
    <tr>
      <td width="100%" valign="top"><br />1.- Instala el paquete apticron<br /><br />
      </td>
    </tr></tbody>
  </table><br /><br />El fichero de configuración lo encontramos en /etc/apticron/apticron.conf, donde podremos indicar la cuenta de correos donde se envían los informes que por defecto es al usuario root (en el ejercicio anterior habíamos hecho las modificaciones necesarias para redirigirlo a otro usuario).<br /><br />Y a partir de aquí, apticron estará listo para comenzar a enviar correos electrónicos una vez al día, con la información de los nuevos paquetes disponibles, el repositorio del paquete, la criticidad, etc. <br /><br />
  <table border="1" width="100%"><tbody>
    <tr>
      <td width="100%" valign="top"><br />1.- Comprueba la configuración en el archivo etc/apticron/apticron.conf<br />2.- Comprueba cuando se ejecuta el programa editando el archivo /etc/cron.d/apticron<br /><br />
      </td>
    </tr></tbody>
  </table><br />
  <h1>Cron-apt</h1>Esta herramienta permite automatizar las tareas de actualización. Mas precisamente, cron-apt es una aplicación que combina las utilidades de cron y apt de forma muy flexible, con el fin de manejar la automatización de apt a través de cron. De la misma forma que apticron, apt-cron también envía correos electrónicos al administrador con los informes obtenidos por la herramienta.<br /><br />Por defecto, cron-apt se ejecuta todos los días realizando dos tareas: primero un “apt-get update” del sistema; seguido de esto, si hubiese actualizaciones para descargar, un “apt-get dist-upgrade -d”.<br /><br />Es decir que realiza la actualización del sistema, descarga los paquetes necesarios resolviendo todas las dependencias necesarias, pero no instala nada de lo descargado. Este ultimo paso requiere la intervención del administrador, ya que cada vez que haya nuevas actualizaciones para instalar, la herramienta enviará un correo electrónico informando del hecho.<br /><br />
  <table border="1" width="100%"><tbody>
    <tr>
      <td width="100%" valign="top"><br />1.- Instala el paquete cron-apt<br />2.- El archivo de configuración de la herramienta es /etc/cron-apt/config, modifícalo para usar aptitude en vez de apt-get y para que se manda las notificaciones por correo al root.<br />Comprueba cuando se ejecuta el programa editando el archivo /etc/cron.d/cron-apt<br /><br />
      </td>
    </tr></tbody>
  </table><br /><br />De esta forma podremos evitarnos la tarea de buscar actualizaciones a daca uno de los paquetes que tenemos instalados en el sistema, ya que recibiremos toda esta información en nuestro correo. Y si estamos de acuerdo con las actualizaciones, solo restará un:<br /><br /># apt-get dist-upgrade<br /><br /></div>
