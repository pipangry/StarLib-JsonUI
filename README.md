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
![App Screenshot](https://i.postimg.cc/jSkcG6Wd/2024-10-19-113144.png)
