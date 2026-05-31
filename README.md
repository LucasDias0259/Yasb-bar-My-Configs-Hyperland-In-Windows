# Yasb-bar-My-Configs-Hyperland-In-Windows

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d9686f41-514b-41aa-867c-de3e3c020f32" />

Hello Everyone My Name Is Lucas I´m a student tecnhology that love to do rice or called (linux customization ) this config was made in windows 11 , if you like you can show or copy this configs in this times , i´m study but sometime i´ll post my other configs , this is first github that i post my configs but i decide someday post my other configs ok see ya have a good one for everyone ... ass: LD

watch_stylesheet: true
watch_config: true
debug: false

komorebi:
  start_command: "komorebic start --whkd"
  stop_command: "komorebic stop --whkd"
  reload_command: "komorebic stop --whkd && komorebic start --whkd"

bars:
  status-bar:
    enabled: true
    screens: ['*'] 
    class_name: "yasb-bar"
    alignment:
      position: "top"
      center: false
    blur_effect:
      enabled: true
      acrylic: true
      dark_mode: true
      round_corners: true
      border_color: "C:/Users/daned/.cache/wal/colors.css"
    window_flags:
      always_on_top: true
      windows_app_bar: true
      hide_on_fullscreen: true
    dimensions:
      width: "99%"
      height: 25
    padding:
      top: 5
      left: 0
      bottom: 0
      right: 0
    widgets:
      left:
        [
