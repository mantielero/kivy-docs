Lists
=====

Introducción
------------

Con este widget podemos crear listas.

En el python::

  from kivymd.list import ILeftBody, ILeftBodyTouch, IRightBodyTouch, BaseListItem

En la cadena KV::

  #:import MDList kivymd.list.MDList
  #:import OneLineListItem kivymd.list.OneLineListItem
  #:import TwoLineListItem kivymd.list.TwoLineListItem
  #:import ThreeLineListItem kivymd.list.ThreeLineListItem
  #:import OneLineAvatarListItem kivymd.list.OneLineAvatarListItem
  #:import OneLineIconListItem kivymd.list.OneLineIconListItem
  #:import OneLineAvatarIconListItem kivymd.list.OneLineAvatarIconListItem
  [...]

  ScrollView:
      do_scroll_x: False
      MDList:
          id: ml
          OneLineListItem:
              text: "One-line item"
          TwoLineListItem:
              text: "Two-line item"
              secondary_text: "Secondary text here"
          ThreeLineListItem:
              text: "Three-line item"
              secondary_text: "This is a multi-line label where you can fit more text than usual"
          OneLineAvatarListItem:
              text: "Single-line item with avatar"
              AvatarSampleWidget:
                  source: './assets/avatar.png'
          TwoLineAvatarListItem:
              type: "two-line"
              text: "Two-line item..."
              secondary_text: "with avatar"
              AvatarSampleWidget:
                  source: './assets/avatar.png'
          ThreeLineAvatarListItem:
              type: "three-line"
              text: "Three-line item..."
              secondary_text: "...with avatar..." + '\\n' + "and third line!"
              AvatarSampleWidget:
                  source: './assets/avatar.png'
          OneLineIconListItem:
              text: "Single-line item with left icon"
              IconLeftSampleWidget:
                  id: li_icon_1
                  icon: 'star-circle'
          TwoLineIconListItem:
              text: "Two-line item..."
              secondary_text: "...with left icon"
              IconLeftSampleWidget:
                  id: li_icon_2
                  icon: 'comment-text'
          ThreeLineIconListItem:
              text: "Three-line item..."
              secondary_text: "...with left icon..." + '\\n' + "and third line!"
              IconLeftSampleWidget:
                  id: li_icon_3
                  icon: 'sd'
          OneLineAvatarIconListItem:
              text: "Single-line + avatar&icon"
              AvatarSampleWidget:
                  source: './assets/avatar.png'
              IconRightSampleWidget:
          TwoLineAvatarIconListItem:
              text: "Two-line item..."
              secondary_text: "...with avatar&icon"
              AvatarSampleWidget:
                  source: './assets/avatar.png'
              IconRightSampleWidget:
          ThreeLineAvatarIconListItem:
              text: "Three-line item..."
              secondary_text: "...with avatar&icon..." + '\\n' + "and third line!"
              AvatarSampleWidget:
                  source: './assets/avatar.png'
              IconRightSampleWidget:

Actualizar la lista
-------------------

https://github.com/kivy/kivy/wiki/Updating-widget-content-from-a-items-list
