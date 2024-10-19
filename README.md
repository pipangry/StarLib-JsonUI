# StarLib-JsonUI
A small library to help you create simple JsonUI forms.
[MIT license](https://choosealicense.com/licenses/mit/)

![Logo](https://i.postimg.cc/qBsh5WjM/model.png)

Scroll down to view full documentation

## Getting started
1. Download latest release and add starlib folder into your ui folder.
2. If you already have the ui_defs file, combine it with the one that comes bundled with starlib
3. Create your first starlib screen!
## server_form.json
```jsonc
  "main_screen_content": {
    "type": "panel",
    "size": [0, 0],
    "controls": [
        {
          "server_form_factory": {
              "type": "factory",
              "control_ids": {
              "long_form": "@server_form.long_form",
              "custom_form": "@server_form.custom_form"
          }
        }
      }
    ]
  },
//we turn to the pre-made starlib screen element by adding @starlib_screen.screen_template
"long_form@starlib_screen.screen_template": {
//in the $button_control, we specify the button element, in this case we use the already made starlib horizontal_button
//it is necessary to specify the $button_control element, otherwise there will be errors
 "$button_control": "starlib_button.horizontal_button"
}
```
## Here's what happened
![App Screenshot](https://i.postimg.cc/jSkcG6Wd/2024-10-19-113144.png?text=App+Screenshot+Here)

Let's change our textures and form size:

```jsonc
//we turn to the pre-made starlib screen element by adding @starlib_screen.screen_template
"long_form@starlib_screen.screen_template": {
  //in the $button_control, we specify the button element, in this case we use the already made starlib horizontal_button
  //it is necessary to specify the $button_control element, otherwise there will be errors
   "$button_control": "starlib_button.horizontal_button",

   //$size controls size of out form
   "$size": [
      320,
      220
   ],

   //$header_size controls size of header element
   "$header_size": [
    "100%",
    28
   ],
   //in $title_font_type we change default font to MinecraftTen font
   "$title_font_type": "MinecraftTen",

   //in $header_texture_control we define element, that will be used as header texture.
   "$header_texture_control": "server_form.my_custom_header",
   //in $background_control we define element, that will be used as background.
   "$background_control": "server_form.my_custom_background"
},

//we turn to the pre-made starlib texture by adding @starlib_style.texture
"my_custom_header@starlib_style.texture": {
//$texture_path is out path to texture
"$texture_path": "textures/example/header"
},

//we turn to the pre-made starlib texture by adding @starlib_style.texture
"my_custom_background@starlib_style.texture": {
//$texture_path is out path to texture
"$texture_path": "textures/example/background"
},
```
And out **RugUI** parody done!

[**RugUI** — one of the most powerful UIs](https://discord.com/channels/523663022053392405/1294631804740964405)

![App Screenshot](https://i.postimg.cc/3NfQySr0/2024-10-19-120223.png?text=App+Screenshot+Here)

Now let's make custom form content

```jsonc
//we turn to the pre-made starlib screen element by adding @starlib_screen.screen_template
"long_form@starlib_screen.screen_template": {"
//in $content_control we define element, which will be used as main form content
"$content_control": "server_form.my_custom_content",

   //$size controls size of out form
   "$size": [
      320,
      200
   ],

   //$header_size controls size of header element
   "$header_size": [
    "100%",
    28
   ],
   //in $title_font_type we change default font to MinecraftTen font
   "$title_font_type": "MinecraftTen",

   //in $header_texture_control we define element, that will be used as header texture.
   "$header_texture_control": "server_form.my_custom_header",
   //in $background_control we define element, that will be used as background.
   "$background_control": "server_form.my_custom_background"
},
```
```jsonc
"my_custom_content": {
  "type": "stack_panel",
  "orientation": "horizontal",
  "size": [
    "100% - 8px",
    "100% - 8px"
  ],
  "collection_name": "form_buttons",
  "controls": [
    {
      //we turn to the pre-made button by adding @starlib_button.default_button
      "big_button@starlib_button.default_button": {
        "$button_size": [
          "50%",
          "100%x"
        ],
        "collection_index": 0
      }
    },
    {
      "horizontal_buttons_panel": {
        "type": "stack_panel",
        "orientation": "vertical",
        "size": [
          "fill",
          "100%sm"
        ],
        "collection_name": "form_buttons",
        "controls": [
          {
            //we turn to the pre-made button by adding @starlib_button.default_button
            "horizontal_button@starlib_button.default_button": {
              "$button_size": [
                "100%",
                "50%"
              ],
              "collection_index": 1
            }
          },
          {
            "small_button_stack": {
              "type": "stack_panel",
              "orientation": "horizontal",
              "size": [
                "100%",
                "fill"
              ],
              "collection_name": "form_buttons",
              "controls": [
                {
                  //we turn to the pre-made button by adding @starlib_button.default_button
                  "smal_button1@starlib_button.default_button": {
                    "$button_size": [
                      "50%",
                      "100%"
                    ],
                    "collection_index": 2
                  }
                },
                {
                  //we turn to the pre-made button by adding @starlib_button.default_button
                  "smal_button2@starlib_button.default_button": {
                    "$button_size": [
                      "50%",
                      "100%"
                    ],
                    "collection_index": 3
                  }
                }
              ]
            }
          }
        ]
      }
    }
  ]
}
```
# Done!
![App Screenshot](https://i.postimg.cc/Wb2byCJj/2024-10-19-123408.png?text=App+Screenshot+Here)

# Documentation

# starlib_screen.json

## @starlib_screen.screen_template
| Parameter | Default Value | Description |
| :-------- | :-------  | :-------------------------------- |
|$size|225, 200|Size of screen template|
|$header_control|starlib_screen.header_template|Element that will act as the header|
|$content_control|starlib_screen.content_template|Element that will act as the main form content|
|$background_control|starlib_style.screen_background|Background element|

## @starlib_screen.header_template
| Parameter | Default Value | Description |
| :-------- | :-------  | :-------------------------------- |
|$header_size|100%, 24|Size of the header element|
|$header_texture_control|starlib_style.header_texture|Element that will act as the header texture|
|$title_control|starlib_style.title_template|Element that will act as form title|
|$title_font_type|MinecraftSeven|starlib_style.title_template Font type|
|$close_button_control|starlib_common.close_button|Close button element|

## @starlib_screen.content_template
| Parameter | Default Value | Description |
| :-------- | :-------  | :-------------------------------- |
|$scrolling_content|starlib_screen.scrolling_content|Scrolling content|
|$button_control|starlib_style.starlib_error_button_control|Button factory element|

# starlib_common.json

## @starlib_common.close_button
| Parameter | Default Value | Description |
| :-------- | :-------  | :-------------------------------- |
|$close_button_texture|starlib_style.close_button_texture|Close button texture|
|$close_button_texture_hover|starlib_style.close_button_texture_hover|Close button texture on hover state|

## @starlib_common.scrolling_panel
| Parameter | Default Value | Description |
| :-------- | :-------  | :-------------------------------- |
|$scrolling_content|starlib_style.starlib_error_scrolling_pane|Scrolling panel content|
|$scrolling_panel_size|100% - 8px, 100% - 8px|Size of the scrolling panel|

## @starlib_common.button_image
| Description |
| :-------------------------------- |
| Form button image |

## @starlib_common.binding
| Parameter | Default Value | Description |
| :-------- | :-------  | :-------------------------------- |
|$key||If there is a $key value in #form_button_text, panel is visible|

## @starlib_common.reverse_binding
| Parameter | Default Value | Description |
| :-------- | :-------  | :-------------------------------- |
|$key||If there is a $key value in #form_button_text, panel isn't visible|

# starlib_button.json

## @starlib_button.button_template
| Parameter | Default Value | Description |
| :-------- | :-------  | :-------------------------------- |
|$default_button_state|starlib_style.button_state_default|Default button element|
|$button_content|starlib_button.button_content|Element that will act as the button content|
|$hover_button_state|starlib_style.button_state_hover|Hover button element|
|$pressed_button_state|starlib_style.button_state_hover|Pressed button element|

## @starlib_button.horizontal_button
| Parameter | Default Value | Description |
| :-------- | :-------  | :-------------------------------- |
|$button_size|100%, 32|Size of the button|

## @starlib_button.default_button
| Parameter | Default Value | Description |
| :-------- | :-------  | :-------------------------------- |
|$button_size|100%y, 100%|Size of the button|

## @starlib_button.button_content
| Parameter | Default Value | Description |
| :-------- | :-------  | :-------------------------------- |
|$button_text_control|starlib_button.button_text_template|Button content text element|

# starlib_style.json

## @starlib_style.texture
| Parameter | Default Value | Description |
| :-------- | :-------  | :-------------------------------- |
|$texture_path|textures/ui/cell_image_darkgrey|Image texture|

## @starlib_style.text
| Description |
| :-------------------------------- |
| Label template |

## @starlib_style.title_template
| Parameter | Default Value | Description |
| :-------- | :-------  | :-------------------------------- |
|$title_font_type|MinecraftSeven|Title font type|

## @starlib_style.form_text
| Description |
| :-------------------------------- |
| Form text template |
