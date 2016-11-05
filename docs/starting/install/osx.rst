.. _install-osx:

Instalando Python en Mac OS X
=============================

La última versión de Mac OS X, El Capitan, **tiene por defecto Python 2.7**.

No necesitas instalar ni configurar nada más para usar Python. Dicho esto, te
recomiendo encarecidamente que instales las herramientas y librerías que se
describen en la siguiente sección antes de empezar a programar en Python. En
particular, siempre deberías instalar Setuptools y pip puesto que hacen la vida
mas fácil al usar librerías de terceros.

La versión de Python proporcionada con OS X está bien para aprender, pero no es
recomendable para el desarrollo. La versión proporcionada con OS X puede estar
desactualizada respecto a la versión `oficial y actual de Python <https://www.python.org/downloads/mac-osx/>`_,
que es la que se considera como estable para el público en general.


Hacerlo bien
--------------

Vamos a instalar una versión real de Python.

Antes de instalar Python, necesitarás instalar GCC. El compilador GCC se puede
 obtener descargando `Xcode <http://developer.apple.com/xcode/>`_, el paquete
 pequeño `Command Line Tools <https://developer.apple.com/downloads/>`_ (debes
 tener una cuenta Apple) o el paquete todavía más pequeño `OSX-GCC-Installer
 <https://github.com/kennethreitz/osx-gcc-installer#readme>`_.

.. note::
    Si ya tienes instalado el paquete Xcode no instales el pquete
    OSX-GCC-Installer. En combinación, pueden probocar problemas de difícil
    diagnóstico.

.. note::
    Si quieres hacer una instalación desde cero de Xcode también necesitarás el
    paquete de "Command Line Tools" ejecutando ``xcode-select --install`` en el
    terminal.

Aunque OS X tiene una gran cantidad de herramientas UNIX, aquellos que estén
familiarizados con sistemas Linux se encontrarán que falta un componente
básico: un gestor de paquetes decente. `Homebrew <http://brew.sh>`_ llena este
hueco.

Para `instalar Homebrew <http://brew.sh/#install>`_ abre :file:`Terminal` o tu
terminal OSX favorito y ejecuta:

.. code-block:: console

    $ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

El script explicará que cambios hará y preguntará antes de que empiece la
instalación.
Una vez hayas instalado Homebrew, añade el directorio de Homebew al principio
de tu variable de entorno :envvar:`PATH` . Puedes hacer esto si añades al final
del fichero :file:`~/.profile` la siguiente linea:

.. code-block:: console

    export PATH=/usr/local/bin:/usr/local/sbin:$PATH

Ahora ya puedes instalar Python 2.7:

.. code-block:: console

    $ brew install python

Esto tomará un minuto o dos. 


Setuptools y Pip
----------------

Homebrew instala Setuptools y ``pip`` por ti. 

Setuptools te permite descargar, instalar y desinstalar cualquier programa
de Python que cumpla las especificaciones con un solo comando
(``easy_install``). Esto también te permite usar la instalación en red para tus propios programas sin demasiado esfuerzo.


``pip`` es una herramienta para instalar y gestionar de manera fácil los
paquetes de Python, que es recomendada por encima de ``easy_install``. Es
superior a ``easy_install`` en `varios aspectos <https://python-packaging-user-guide.readthedocs.org/en/latest/pip_easy_install/#pip-vs-easy-install>`_ y está mantenida activamente.


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
