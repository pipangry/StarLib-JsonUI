# StarLib-JsonUI
A small library to help you create simple JsonUI forms.
[MIT license](https://choosealicense.com/licenses/mit/)

![Logo](https://i.postimg.cc/505tF3Lx/model.png)

## Getting started
1. add starlib folder into your ui folder.
2. if you already have the ui_defs file, combine it with the one that comes bundled with starlib
3. create your first starlib screen:
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
