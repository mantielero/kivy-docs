TextField
=========

Introducción
------------

Lo primero es importar el módulo adecuado::

  #:import MDTextField kivymd.textfields.MDTextField

En algún momento, querremos solicitar información. Para ello haremos::


  MDTextField:
      id: my_entry
      hint_text: "Primer Apellido"

Podemos añadir un ayuda::

  MDTextField:
      hint_text: "Helper text on focus"
      helper_text: "This will disappear when you click off"
      helper_text_mode: "on_focus"

El modo del **helper_text** puede ser:

- on_focus
- persistent
- on_error: este caso requiere que exista una función de validación.

Se puede limitar la longitud del campo::

      max_text_length: 10

Se puede hacer obligatorio:

      required: True

Puede requerir múltiples líneas::

      multiline: True

Puede deshabilitarse::

      disabled: True

Colores:

  color_mode: 'accent'

o bien:

  color_mode: 'custom'
  line_color_focus: self.theme_cls.opposite_bg_normal  # This is the color used by the textfield



on_error
--------

En el KV tenemos::

  MDTextField:
      id: text_field_error
      hint_text: "Helper text on error (Hit Enter with two characters here)"
      helper_text: "Two is my least favorite number"
      helper_text_mode: "on_error"

Para que se comporte como esperamos hacemos::

  def build(self):
      main_widget = Builder.load_string(main_widget_kv)
      # self.theme_cls.theme_style = 'Dark'

      main_widget.ids.text_field_error.bind(
          on_text_validate=self.set_error_message,
          on_focus=self.set_error_message)
      self.bottom_navigation_remove_mobile(main_widget)
      return main_widget

  def set_error_message(self, *args):
      if len(self.root.ids.text_field_error.text) == 2:
          self.root.ids.text_field_error.error = True
      else:
          self.root.ids.text_field_error.error = False
