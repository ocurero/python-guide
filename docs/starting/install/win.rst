.. _install-windows:

Instalar Python en Windows
==========================


Primero descarga la `ùltima versión <https://www.python.org/ftp/python/2.7.10/python-2.7.10.msi>`_
de Python 2.7 desde la página oficial. Si quieres estar seguro de que estás
instalando la versión mas actualizada, haz clic en el enlace Descargas > Windows
desde la `página principal de Python <http://python.org>`_ .

La versión para Windows es un paquete MSI. Para instalarlo manualmente, haz
doble clic en el fichero. Los paquetes MSI permiten a los administradores
automatizar las instalaciones con las herramientas estándar.

Por diseño, Python se instala en un directorio con la versión incluida. Por
ejemplo, Python 2.7 se instalará en :file:`C:\\Python27\\` de manera que pueda
convivir con diferentes versiones sin problema. Obviamente, sólo puede haber un
interprete por defecto para los archivos de Python. Tampoco se modifica
automaticamente la variable de entorno :envvar:`PATH`, de manera que siempre
tienes el control de qué versión de Python quieres que se ejecute.

Escribir la ruta completa al interprete de Python una y otra vez es tedioso,
así que añade los directorio de tu interprete de Python por defecto a la
variable :envvar:`PATH`. Suponiendo que tu instalación por defecto está en
directorio :file:`C:\\Python27\\`, añade lo siguiente a tu variable de entorno
:envvar:`PATH`:

.. code-block:: console

    C:\Python27\;C:\Python27\Scripts\

Puedes hacer esto ejecutando el siguiente comando en una sesión ``powershell``:

.. code-block:: console

    [Environment]::SetEnvironmentVariable("Path", "$env:Path;C:\Python27\;C:\Python27\Scripts\", "User")

El segundo directorio (:file:`Scripts`) recibe comandos cuando se instalan
ciertos paquetes, de manera que es muy recomendable añadirlo también.

No necesitas instalar ni configurar nada más para usar Python. Dicho esto, te
recomiendo encarecidamente que instales las herramientas y librerías que se
describen en la siguiente sección antes de empezar a programar en Python. En
particular, siempre deberías instalar Setuptools y pip puesto que hacen la vida
mas fácil al usar librerías de terceros.

Setuptools y Pip
----------------

Las dos librerías de paquetes externas más importantes son `setuptools <https://pypi.python.org/pypi/setuptools>`_
 y `pip <https://pip.pypa.io/en/stable/>`_.

Una vez instaladas, puedes descargar, instalar y desinstalar cualquier programa
de Python que cumpla las especificaciones con un solo comando. Esto también te
permite usar la instalación en red para tus propios programas sin demasiado
esfuerzo.

Python 2.7.9 y posteriores (en la versión 2 de Python) y Python 3.4 y
posteriores incluyen el paquete pip de forma predeterminada.

Para saber si el paquete pip está instalado, abre un terminal y ejecuta:

.. code-block:: console

    $ command -v pip

Para instalar pip, `sigue la guia oficial de pip <https://pip.pypa.io/en/latest/installing/>`_.
Al instalar pip también se instalará la ultima versión del paquete setuptools.


Entornos virtuales
------------------

Un entorno virtual es una herramienta para crear entornos de Python de manera
que las dependencias requeridas por diferentes proyectos estén separadas. Esto
soluciona problemas del estilo "el proyecto X depende de la versión 1.x pero el
proyecto Y necesita la versión 2.x" y permite mantener tu directorio de
paquetes globales (site-packages) limpio.

Por ejemplo, puedes trabajar en un proyecto que requiere Django 1.3 mientras
que otro requiere Django 1.0.

Para usar entornos virtuales y tener más información, visita la documentación :ref:`Virtual Environments <virtualenvironments-ref>`.

También puedes usar :ref:`virtualenvwrapper <virtualenvwrapper-ref>` para que
sea más sencillo gestionar tus entornos virtuales.

--------------------------------

Esta página es una mezcla de versiones de `otra guia <http://www.stuartellis.eu/articles/python-development-windows/>`_,
que está disponible bajo la misma licencia.
