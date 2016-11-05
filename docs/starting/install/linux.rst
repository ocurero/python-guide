.. _install-linux:

Instalar Python en Linux
==========================

Las ultimas versiones de CentOS, Fedora, Redhat Enterprise (RHEL) y Ubuntu      
**ya tienen Python 2.7 por defecto**.

Para saber qué versión de Python está instalada, abre una ventana de símbolo
de sistema y ejecuta:

.. code-block:: console

    $ python --version

Algunas versiones antiguas de RHEL y CentOS tienen Python 2.4, que es demasiado
antiguo para el desarrollo actual de Python. Afortunadamente hay paquetes extra
para `Extra Packages for Enterprise Linux`_ que incluyen paquetes de mucha calidad basados en Fedora. Este repositorio contiene Python 2.6 específicamente diseñado para ser instalado junto con la instalación de Python 2.4 del propio sistema operativo.

.. _Extra Packages for Enterprise Linux: http://fedoraproject.org/wiki/EPEL

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

