Screen Manager
==============

Introducción
------------

El objetivo es poder representar dos contenidos y mostrar uno y otro a voluntad.


Un ejemplo sencillo (aunque lo complica un poco el hecho de usar Toolbars en lugar de botones) es::

  #!/usr/bin/env python
  # -*- coding: utf-8 -*-
  from kivy.app import App
  from kivy.lang import Builder
  from kivymd.theming import ThemeManager
  from kivy.properties import ObjectProperty
  from kivy.uix.boxlayout import BoxLayout

  class MyLayout(BoxLayout):

      scr_mngr = ObjectProperty(None)

      def change_screen(self, screen, *args):
          self.scr_mngr.current = screen

  main_widget_kv = '''
  #:import Toolbar kivymd.toolbar.Toolbar
  #:import partial functools.partial

  MyLayout:
      orientation: 'vertical'
      scr_mngr: scr_mngr
      Toolbar:
          id: toolbar
          title: 'My Toolbar'
          md_bg_color: app.theme_cls.primary_color
          background_palette: 'Primary'
          background_hue: '500'
          left_action_items: [['arrow-left',  partial(root.change_screen, 'screen1') ]]
          right_action_items: [['arrow-right',  partial(root.change_screen, 'screen2') ]]
      ScreenManager:
          id: scr_mngr
          Screen:
              name: 'screen1'
              Toolbar:
                  title: "Screen 1"
          Screen:
              name: 'screen2'
              Toolbar:
                  title: "Screen 2"
  '''

  class KitchenSink(App):
      theme_cls = ThemeManager()
      title = "My kivy app"

      def build(self):
          main_widget = Builder.load_string(main_widget_kv)
          # self.theme_cls.theme_style = 'Dark'
          print(self.root)
          return main_widget

  if __name__ == '__main__':
      KitchenSink().run()

¿Por qué es complicado?
-----------------------

https://stackoverflow.com/questions/47767671/kivy-kv-screenmanager-changing-the-current-screen

https://github.com/kivy/kivy/issues/5532
