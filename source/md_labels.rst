Labels
======

Introducción
------------

Ahora que añadimos contenido sencillo. Las etiquetas, por ejemplo:

Para añadir una etiqueta basta::

  MDLabel:
      font_style: 'Body1'
      theme_text_color: 'Primary'
      text: "Body1 label"
      halign: 'center'

El font_style puede ser:

- Body1
- Body2
- Caption
- Subhead
- Title
- Headline
- Display1, Display2, Display3, Display4

Para el color:

- Primary
- Secondary
- Hint
- Error
- o::

  theme_text_color: 'Custom'
  text_color: (0,1,0,.4)

En cuanto a tamaños, también podemos añadir algo del tipo::

  size_hint_y: None
  height: self.texture_size[1] + dp(4)
