ScrollView
==========

Introducción
------------

Rápidamente podemos llegar a la situación en la que no cabe en la pantalla aquello que queremos mostrar. En esa situación, podemos hacer algo como lo que sigue:


Hacemos::

  Screen:
      name: 'labels'
      ScrollView:
          do_scroll_x: False
          BoxLayout:
              orientation: 'vertical'
              size_hint_y: None
              height: dp(1000)
              BoxLayout:
                  [....]

.. note::

   A continuación, vemos BoxLayout.
   
