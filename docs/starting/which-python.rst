Escoger un interprete 
=====================

.. _which-python:

El estado de Python (2 o 3)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Al escoger el interprete de Python siempre surge la misma pregunta: 
"¿Deberia escoger Python 2 o Python 3?" La respuesta no es tan obvia como
podria parecer.

El resumen de la situación actual es la siguiente:   

1. Python 2.7 ha sido el estandar durante *mucho* tiempo
2. Python 3 introdujo cambios sustanciales en el lenguaje con los que muchos programadores no estan de acuerdo.
3. Python 2.7 recibirá actualizaciones de seguridad hasta 2020 [#pep373_eol]_.
4. Python 3 está constantemente evolucionando, igual que Python 2 lo hizo en el
   pasado.

Como puedes ver, no es una decisión fácil.


Recomendaciones
~~~~~~~~~~~~~~~

Seré directo:

**Usa Python 3 si...**

- No te importa.
- Te gusta Python 3.
- No tienes ninguna preferencia respecto a Python 2 o 3.
- No sabes cual usar.             
- Tu gustan los cambios.

**Usa Python 2 si...**

- Te gusta Python 2 y no estas de acuerdo con que el futuro sea Python 3.
- Los requerimientos de estabilidad de tu software se verian aumentados por un lenguaje y entorno que nunca cambia.      
- Software del cual dependes lo requiere.


¿Por lo tanto.... 3?
~~~~~~~~~

Si tienes que elegir un interprete y no tienes ninguna preferencia, yo
recomiendo que uses la última versión de Python 3.x ya que cada nueva versión
introduce novedades en la librería estándar de y correcciones de fallos y 
seguridad. Al fin y al cabo, el progreso es progreso.   

Por lo tanto, solo usa Python 2 si tienes una verdadera razón para hacerlo. Por
ejemplo, porque una librería de Python 2 no tiene una alternativa real en 
Python 3 o, como yo, porque te encanta Python 2.

Visita `Can I Use Python 3? <https://caniusepython3.com/>`_ para ver si hay
algún software del cual dependes no te permitirá cambiar a Python 3.

`Continua leyendo <http://wiki.python.org/moin/Python2orPython3>`_

Es posible escribir `codigo que funciona tanto en Python 2.6, 2.7 y Python 3
<https://docs.python.org/3/howto/pyporting.html>`_. Los cambios necesarios van
desde cambios triviales a complejos dependiendo del tipo de software que estas
escribiendo. De todas maneras, si eres principiante, hay cosas mucho más importantes. 

Implementaciones
~~~~~~~~~~~~~~~~

Cuando la gente habla de *Python* se refieren no solo al lenguaje sino también 
a la implementación de CPython. *Python* es una especificación de un lenguaje
que se puede implementar de muchas maneras diferentes.

CPython
-------

`CPython <http://www.python.org>`_ es la implementación de refererencia de 
Python escrita en C. Compila el código Python a un bytecode intermedio que
luego se interpreta en una maquina virtual. CPython proporciona la mayor
compatibilidad con paquetes de Python y extensiones en C.

Si estas escribiendo código libre en Python y quieres que llegue a una
audiencia mayor, usar CPython es lo más recomendable. Para usar paquetes que
dependen de extensiones en C para funcionar, CPython es tu única implementación
posible.

Todas las versiones del lenguaje Python estan implementadas en C porque CPython
es la implementación de referencia.

PyPy
----

`PyPy <http://pypy.org/>`_ es un interprete de Python estáticamente tipado
implementado en un subconjunto limitado del lenguaje llamado RPython. El
interprete proporciona un compilador en tiempo de ejecución (just-in-time) y lo
traduce a un lenguaje demás bajo nivel, tal como C, LLVM o MSIL.

PyPy intenta mantener la máxima compatibilidad con la implementación de
referencia CPython y al mismo tiempo mejorar el rendimiento.

Si quieres mejorar el rendimiento de tu código Python, una posibilidad es
probar PyPy. En una serie de comparativas, es actualmente `cinco veces más rápido 
que CPython <http://speed.pypy.org/>`_.

PyPy soporta Python 2.7. PyPy3 [#pypy_ver]_, publicado como beta, se centra en Python 3.

Jython
------

`Jython <http://www.jython.org/>`_ es una implementación de Python que compila
el código Python a bytecode de Java que luego se ejecuta en la maquina virtual
de java (JVM). Además, es posible importar y usar cualquier clase de Java como
si fueran módulos de Python.

Si necesitas interactuar con código Java o tienes que escribir código para la
maquina virtual de java, Jython es la mejor opción.

Jython actualmente soporta Python 2.7. [#jython_ver]_

IronPython
----------

`IronPython <http://ironpython.net/>`_  es una implementación de Python para la
plataforma .NET. Puede usar tanto las librerías de Python como las de .NET y
también puede exponer el código de Python a otros lenguajes en la plataforma de
.NET.

`Python Tools para Visual Studio <http://ironpython.net/tools/>`_ integra
IronPython directamente en el entorno de desarrollo de Visual Studio, perfecto
para los programadores en Windows.

IronPython soporta Python 2.7. [#iron_ver]_

PythonNet
---------

`Python para .NET <http://pythonnet.github.io/>`_ es un paquete que
proporciona una integración casi perfecta entre una instalación nativa de
Python y el .NET Common Language Runtime o CLR ("Entorno en tiempo de ejecución de lenguaje común"). Es la solución inversa tomada por IronPython (ver arriba), donde es más un complemento que una alternativa.

En compañía de Mono, PythonNet permite ejecutar código Python en sistemas
operativos diferentes de Windows, como OS X y Linux, bajo la plataforma .NET.
Puede usarse junto con IronPython sin ningún problema.

PythonNet soporta desde Python 2.3 hasta Python 2.7. [#pythonnet_ver]_

.. [#pypy_ver] http://pypy.org/compat.html

.. [#jython_ver] https://hg.python.org/jython/file/412a8f9445f7/NEWS

.. [#iron_ver] http://ironpython.codeplex.com/releases/view/81726

.. [#pythonnet_ver] http://pythonnet.github.io/readme.html

.. [#pep373_eol] https://www.python.org/dev/peps/pep-0373/#id2
