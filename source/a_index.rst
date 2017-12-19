Android
=======

Introducción
------------

https://github.com/kivy/buildozer

https://kivy.org/docs/guide/packaging-android.html

Buildozer
---------

Instalación
^^^^^^^^^^^

Lo instalamos::

    $ yaourt -S python-buildozer

Para Android, además necesitamos los siguientes paquetes en la arquitectura x64

- Cython
- build-libs
- Java SDK

En archlinux, alguno de las siguientes paquetes podrían faltar:

- jdk7-openjdk
- python
- python-pip
- python-kivy
- mesa-libgl
- lib32-mesa-libgl
- lib32-sdl2
- lib32-sdl2_image
- lib32-sdl2_mixer
- sdl2_ttf
- unzip
- gcc-multilib
- gcc-libs-multilib
- **cython==0.25**::

   $ sudo pip install /home/jose/Descargas/Cython-0.25.tar.gz

El NDK es el Native Development Kit. El soporte de python3 se consigue con `CrystaX NDK <https://www.crystax.net/en/android/ndk>`_, que es un drop-in replacement.

Descargamos el crystax en un directorio, que será al que apuntaremos en el path en el fichero **buuldozer.spec**.

Primer proyecto
^^^^^^^^^^^^^^^

Creamos la carpeta de nuestro proyecto::

   $ mkdir ex01
   $ cd ex01
   $ buildozer init

Esto crea el fichero **buildozer.spec**.

Creamos un fichero de ejemplo **main.py**::

   __version__ = “1.0”
   from kivy.app import App
   from kivy.uix.button import Button

   class Hello(App):
       def build(self):
           btn = Button(text='Hello World')
           return  btn

   Hello().run()

Comprobamos que la aplicación funciona en linux::

   $ python main.py

Editamos el fichero **buildozer.spec** (nombre, desarrollador, ...)::

   [app]

   # (str) Title of your application
   title = My Application

   # (str) Package name
   package.name = myapp

   # (str) Package domain (needed for android/ios packaging)
   package.domain = org.test

   # (str) Source code where the main.py live
   source.dir = .

   # (str) Application versioning (method 1)
   version = 0.1

   # Require python3crystax:
   requirements = python3crystax==3.6,kivy

   # Point to the directory where you extracted the crystax-ndk:
   android.ndk_path = <Your install path here.  Use ~ for home DIR>

Construimos el fichero **apk** mediante::

   $ buildozer -v android debug

y cuando termina, genera el fichero::

   .buildozer/android/platform/build/dists/myapp/build/outputs/apk/myapp-debug.apk


.. warning:: Esto descarga un montón de paquetes. Es un proceso lento.


También podemos ejecutar (construye, envía y ejecuta)::

   $ buildozer android debug deploy run


Genymotion
----------



Sirve para simular dispositivos. Si arrancamos un dispositivo en Genymotion, podemos ejecutar::

   $ adb devices
   List of devices attached
   192.168.56.102:5555	device

Y para instalar la aplicación::

   $ adb install .buildozer/android/platform/build/dists/myapp/build/outputs/apk/myapp-debug.apk


.. warning::

   Si falla con algo como::

      [INSTALL_FAILED_NO_MATCHING_ABIS: Failed to extract native libraries, res=-113]

   Es que estamos instalando arm en Intel!!

   Eso lo ajustamos en **buildozer.spec**::

      # (str) The Android arch to build for, choices: armeabi-v7a, arm64-v8a, x86
      android.arch = armeabi-v7a
