Toolbar
=======

Introducción
------------

En las toolbar podemos poner iconos que realizan acciones. Una toolbar en KV, tiene la siguiente pinta::

  #:import Toolbar kivymd.toolbar.Toolbar

  Toolbar:
      id: toolbar
      title: 'My Toolbar'
      md_bg_color: app.theme_cls.primary_color
      background_palette: 'Primary'
      background_hue: '500'

Propiedades
-----------

Action items
^^^^^^^^^^^^

En la toolbar añadimos elementos (iconos) que inician acciones. Los botones a la izquierda se añaden mediante la siguiente lista::

  left_action_items: [['arrow-left', lambda x: None]]

Los botones de la toolbar en el lado derecho se añaden también como una lista::

  right_action_items: [['lock', lambda x: None], \
      ['camera', lambda x: None], \
      ['play', lambda x: None], \
      ['content-copy', lambda x: None]]

En estos ejemplos vemos que los botones no hacen nada::

  lambda x: None

En casos reales lo que haremos será llamar a funciones que hagan cosas útiles. Por ejemplo::

  left_action_items: [['menu', lambda x: app.root.toggle_nav_drawer()]]
  right_action_items: [['dots-vertical', lambda x: app.root.toggle_nav_drawer()]]

En el primer caso, se usa el icono *'menu'* y en el segundo el icono de los puntos verticales (dots-vertical). En ambos casos se hace un *toggle* de un drawer. Un drawer es el típico menú que aparece lateralmente en los móviles.









Posicionamiento
^^^^^^^^^^^^^^^

Podemos ubicar la toolbar mediante::

  pos_hint: {'center_x': 0.5, 'center_y': 0.75}



Colores
^^^^^^^

Existen diferentes formas de definir los colores. Los principales propiedades relacionadas son:

- md_bg_color
- background_palette
- background_hue

En el primer caso, podemos encontrar::

  md_bg_color: app.theme_cls.primary_color

ó::

  #:import get_color_from_hex kivy.utils.get_color_from_hex
  [...]
  md_bg_color: get_color_from_hex(colors['Teal']['500'])


En cuanto a la paleta: 'Primary', 'Teal', 'Amber', 'DeepPurple', ...

.. note::

   ¿De dónde se saca esta lista de colores?

.. note::

  ¿Qué es el hue? Y qué representa: '500', '700', 'A400', ...
