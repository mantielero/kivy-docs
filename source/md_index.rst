Material Design
===============

Introducción
------------

Contiene una serie de widgets basados en el Material Design de Google, pero usando Kivy. El proyecto en cuestión es `KivyMD <https://gitlab.com/kivymd/KivyMD>`_.

Aplicación mínima
-----------------

Como ejemplo creamos una aplicación que nos muestra una Toolbar de las que proporciona KivyMD::

  #!/usr/bin/env python
  # -*- coding: utf-8 -*-
  from kivy.app import App
  from kivy.lang import Builder
  from kivymd.theming import ThemeManager

  main_widget_kv = '''
  #:import Toolbar kivymd.toolbar.Toolbar

  BoxLayout:
      orientation: 'vertical'
      Toolbar:
          id: toolbar
          title: 'My Toolbar'
          md_bg_color: app.theme_cls.primary_color
          background_palette: 'Primary'
          background_hue: '500'
  '''

  class KitchenSink(App):
      theme_cls = ThemeManager()
      title = "My kivy app"

      def build(self):
          main_widget = Builder.load_string(main_widget_kv)
          # self.theme_cls.theme_style = 'Dark'
          return main_widget

  if __name__ == '__main__':
      KitchenSink().run()

Si miramos **showcase** podemos ver la configuración de las toolbar.


.. toctree::
   :maxdepth: 2
   :caption: Contenido

   md_toolbar
   md_screenmanager
   md_labels
   md_scrollview
   md_boxlayout
   md_textfield
   md_selectioncontrols
   md_buttons
   md_list
   
