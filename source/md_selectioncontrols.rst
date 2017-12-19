Selection Controls
==================

Introducción
------------

Tenemos varios tipos de controles::

      MDCheckbox:
          id:            chkbox
          size_hint:    None, None
          size:        dp(48), dp(48)
          pos_hint:    {'center_x': 0.5, 'center_y': 0.4}
          active: True
      MDCheckbox:
          id:            grp_chkbox_1
          group:        'test'
          size_hint:    None, None
          size:        dp(48), dp(48)
          pos_hint:    {'center_x': 0.25, 'center_y': 0.5}
      MDCheckbox:
          id:            grp_chkbox_2
          group:        'test'
          size_hint:    None, None
          size:        dp(48), dp(48)
          pos_hint:    {'center_x': 0.5, 'center_y': 0.5}
      MDSwitch:
          size_hint:    None, None
          size:        dp(36), dp(48)
          pos_hint:    {'center_x': 0.75, 'center_y': 0.5}
          _active:        False

.. warning::

   ¿Qué controla que sea cuadrado o redondo? El primero era cuadrado y los siguientes redondos. El último es un switch.
