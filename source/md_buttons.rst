Buttons
=======

Introducción
------------

Hay diferentes tipos de botones::


  BoxLayout:
      size_hint: None, None
      size: '88dp', '48dp'
      padding: '12dp'
      pos_hint: {'center_x': 0.75, 'center_y': 0.8}
      MDLabel:
          font_style: 'Body1'
          theme_text_color: 'Primary'
          text: "Disable buttons"
          size_hint_x:None
          width: '56dp'
      MDCheckbox:
          id: disable_the_buttons
  MDIconButton:
      icon: 'sd'
      pos_hint: {'center_x': 0.25, 'center_y': 0.8}
      disabled: disable_the_buttons.active
  MDFlatButton:
      text: 'MDFlatButton'
      pos_hint: {'center_x': 0.5, 'center_y': 0.6}
      disabled: disable_the_buttons.active
  MDRaisedButton:
      text: "MDRaisedButton"
      elevation_normal: 2
      opposite_colors: True
      pos_hint: {'center_x': 0.5, 'center_y': 0.4}
      disabled: disable_the_buttons.active
  MDFloatingActionButton:
      id:                    float_act_btn
      icon:                'plus'
      opposite_colors:    True
      elevation_normal:    8
      pos_hint:            {'center_x': 0.5, 'center_y': 0.2}
      disabled: disable_the_buttons.active

En este ejemplo, vemos cómo controlar si los botones están habilitados o no con un checkbox.
