# Yasb-bar-My-Configs-Hyperland-In-Windows

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d9686f41-514b-41aa-867c-de3e3c020f32" />

Hello Everyone My Name Is Lucas I´m a student tecnhology that love to do rice or called (linux customization ) this config was made in windows 11 , if you like you can show or copy this configs in this times , i´m study but sometime i´ll post my other configs , this is first github that i post my configs but i decide someday post my other configs ok see ya have a good one for everyone ... ass: LD

Windows Rice + GlazeWm + Pywal

# ... o resto das suas configurações gerais da barra (bars, layout, etc) vem aqui abaixo ...

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
          "windows_workspaces",
          "taskbar",         
        ]
      center: 
        [
          "update",
          "clock",

          
                      ]
      right:
        [
          "systray",
          "grouped_widgets",
          "glazewm_tiling_direction",
          "wallpapers",
          "volume",
          "showkeyboard",
          "active_window",
          "battery",
          "notifications",
        ]
widgets:
  

  active_window:
    type: "yasb.active_window.ActiveWindowWidget"
    options:
      label: ""
      label_alt: ""
      label_no_window: ""
      label_icon: true
      label_icon_size: 14
      max_length: 36
      max_length_ellipsis: "..."
      monitor_exclusive: true
  
  clock:
    type: "yasb.clock.ClockWidget"
    options:
      label: "<span>\ue62a</span>{ %a, %d %b (%H:%M)}"
      label_alt: "<span>\ue62a</span>{ %d/%m/%y (%H:%M)}"

      timezones: ["America/Sao_Paulo"]
      calendar:
        blur: false
        round_corners: false
        alignment: "center"
        direction: "down"
        offset_top: 0
        offset_left: 0
        border_color: "#FFD6D1"
        show_holidays: true
        holiday_color: "#e78284"
        country_code: "BR"
      animation:
        enabled: True

  disk:
    type: "yasb.disk.DiskWidget"
    options:
        label: "<span>\uf0c7</span>"
        label_alt: "<span>\udb82\ude23</span>"
        update_interval: 60
        group_label:
          volume_labels: ["C", "D", "E", "F"]
          show_label_name: true
          blur: True
          round_corners: True
          round_corners_type: "small"
          border_color: "System"
          alignment: "right"
          direction: "down"
          distance: 6
        callbacks:
          on_left: "toggle_group"
          on_middle: "toggle_label"
  
  
  systray:
      type: "yasb.systray.SystrayWidget"
      options:
        class_name: "systray"
        label_collapsed: "\uf0a8"
        label_expanded: "\uf0a9"
        label_position: "left"
        icon_size: 17
        pin_click_modifier: "alt"
        show_unpinned: false
        show_unpinned_button: true
        show_battery: false
        show_volume: false
        show_network: false
        tooltip: true
        
  notifications:
      type: "yasb.notifications.NotificationsWidget"
      options:
        label: "<span>\uf476</span> {count}"
        label_alt: "{count} notifications"
        hide_empty: true
        tooltip: true
        callbacks:
          on_left: "toggle_notification"
          on_right: "do_nothing"
          on_middle: "toggle_label"
    

  battery:
      type: "yasb.battery.BatteryWidget"
      options:
        label: "{icon} {percent}%"
        label_alt: "{icon} {percent}% | time: {time_remaining}"
        update_interval: 5000
        hide_unsupported: True
        time_remaining_natural: True
        animation:
          enabled: false
          duration: 0       
        charging_options:
          icon_format: "{charging_icon}"
        status_icons:
          icon_charging: "\udb85\udc0c"
          icon_critical: "\ueba1"
          icon_low: "\ueba3"
          icon_medium: "\ueba6"
          icon_high: "\ueba9"
          icon_full: "\uebaa"
        status_thresholds:
          critical: 10
          low: 25
          medium: 75
          high: 95
          full: 100
  

  update:
      type: "yasb.update_check.UpdateCheckWidget"
      options:
        winget_update:
          enabled: true
          label: "<span>\uf0ab</span>{count}"
          interval: 30
          exclude: []
        windows_update:
          enabled: true
          label: "<span>\uf0ab</span>{count}"
          interval: 240
          exclude: []

  memory:
    type: "yasb.memory.MemoryWidget"
    options:
      label: "<span>\uefc5</span> {virtual_mem_percent}%"
      label_alt: "VIRT: {virtual_mem_percent}% SWAP: {swap_mem_percent}%"
      update_interval: 5000
      progress_bar:
        enabled: false
        size: 8
        thickness: 2
        color: none
        background_color: none 
      callbacks:
        on_left: "toggle_label"
      memory_thresholds:
        low: 25
        medium: 50
        high: 90
  cpu:
    type: "yasb.cpu.CpuWidget"
    options:
      label: "<span>\uf4bc</span> {info[percent][total]:.0f}%"
      label_alt: "CPU {info[percent][total]:.0f}%"
      progress_bar:
        enabled: false
        position: "left"
        size: 8
        thickness: 2
        color: none
        background_color: none
      update_interval: 2000
      callbacks:
        on_right: "do_nothing"
  grouped_widgets:
    type: "yasb.grouper.GrouperWidget"
    options:
      class_name: "grouped-widgets"
      widgets: [
        "memory",
        "cpu",
        "wifi",
        "bluetooth",
        "disk",
      ]
      container_padding:
        top: 0
        left: 0
        bottom: 0
        right: 0


  volume:
        type: "yasb.volume.VolumeWidget"
        options:
          label: "{level}"
          label_alt: "{volume}"
          progress_bar:
            enabled: true
            position: "left"
            size: 14
            thickness: 2
            color: "#94e2d5"
            background_color: "#242739" 
          callbacks:
            on_right: "exec cmd.exe /c start ms-settings:sound"

    

  windows_workspaces:
        type: "yasb.windows_desktops.WorkspaceWidget"
        options:
          label_workspace_btn: "\udb84\udcac"
          label_workspace_active_btn: "\ue62a"
          btn_shadow:
            enabled: true
            color: "black"
            radius: 1
            offset: [ 1, 1 ]


  taskbar:
        type: "yasb.taskbar.TaskbarWidget"
        options:
          icon_size: 17
          animation:
            enabled: true
          preview:
            enabled: true
            width: 350
            delay: 400
            padding: 15
          callbacks:
            on_middle: "close_app"



  showkeyboard:
      type: "yasb.custom.CustomWidget"
      options:
        label: "\udb80\udf13"
        label_alt: ""
        class_name: "showkeyboard-widget"
        callbacks:
          on_left: "exec cmd /c osk"
  
  bluetooth:
      type: "yasb.bluetooth.BluetoothWidget"
      options:
        label: "<span>{icon}</span>"
        label_alt: "<span>\udb82\uded4</span>{device_name}"
        icons:
          bluetooth_on: "\udb80\udcb0"
          bluetooth_off: "\udb80\udcb2"
          bluetooth_connected: "\uf293"
        callbacks:
          on_right: "exec cmd.exe /c start ms-settings:bluetooth"


  wifi:
    type: "yasb.wifi.WifiWidget"
    options:
      label: "<span>{wifi_icon}</span>"
      label_alt: "{wifi_name} {wifi_strength}%"
      update_interval: 5000
      callbacks:
        on_left: "toggle_menu"
        on_middle: "exec cmd.exe /c start ms-settings:network"
        on_right: "toggle_label"
      ethernet_label: "<span>{wifi_icon}</span>"
      ethernet_label_alt: "<span>{wifi_icon}</span>{ip_addr}"
      ethernet_icon: "\ueba9"
      get_exact_wifi_strength: false  # Optional. Will require location access permission if true.
      wifi_icons: [
        "\udb82\udd2e",  # Icon for 0% strength
        "\udb82\udd1f",  # Icon for 1-24% strength
        "\udb82\udd22",  # Icon for 25-49% strength
        "\udb82\udd25",  # Icon for 50-74% strength
        "\udb82\udd28"   # Icon for 75-100% strength
      ]
      label_shadow:
        enabled: true
        color: "black"
        radius: 3
        offset: [ 1, 1 ]
      menu_config:
        blur: true
        round_corners: true
        round_corners_type: "normal"
        border_color: "System"
        alignment: "right"
        direction: "down"
        offset_top: 6
        offset_left: 0
        wifi_icons_secured: [
          "\ue670",
          "\ue671",
          "\ue672",
          "\ue673",
        ]
        wifi_icons_unsecured: [
          "\uec3c",
          "\uec3d",
          "\uec3e",
          "\uec3f",
        ]

  grouper-test:
    type: "yasb.grouper.GrouperWidget"
    options:
      class_name: "grouper-test"
      widgets: [
        "bluetooth",
        "microphone"
      ]
      collapse_options:
        enabled: true
        exclude_widgets: ["battery"]  # Battery widget stays visible when collapsed
        expanded_label: "\udb83\udcde"
        collapsed_label: "\udb83\udce0"
        label_position: "right"

  wallpapers:
    type: "yasb.wallpapers.WallpapersWidget"
    options:
      label: "<span>\uf043</span>"
      # Example path to folder with images. Can be a single string or a list of strings.
      # image_path: "C:\\Users\\{Username}\\Images" 
      image_path: 
        - "C:\\Users\\daned\\OneDrive\\Imagens\\custom wallpapers"
      change_automatically: false # Automatically change wallpaper
      update_interval: 60 # If change_automatically is true, update interval in seconds
      engine:
        enabled: true
        animation: "slide_top" # # circle/slide_top/diamond/split
      gallery:
          enabled: true
          blur: true
          image_width: 220
          image_per_page: 6
          gallery_columns: 0 # 0 = auto, matches image_per_page for a single row
          horizontal_position: "center" # left/center/right placement on screen
          vertical_position: "center" # top/center/bottom placement
          position_offset: 0 # minimum gap (px) from screen edges - see below for advanced options
          respect_work_area: true # clamp to OS work area (avoids Windows taskbar)
          show_buttons: false
          orientation: "portrait"
          image_spacing: 8
          lazy_load: true
          lazy_load_fadein: 100
          image_corner_radius: 6
      # Note: do not use run_after: command if you don't know what it does
    run_after: # List of functions to run after wallpaper is updated
      - "wal -s -t -e -q -n -i {image}" # Example command to run after wallpaper is updated
      - "cmd.exe /c start /min pwsh ./yasb.ps1/" # Example command to run after wallpaper is updated
    callbacks:
      on_left: "toggle_gallery"
      on_middle: "do_nothing"
      on_right: "change_wallpaper"

  glazewm_tiling_direction:
    type: "glazewm.tiling_direction.GlazewmTilingDirectionWidget"
    options:
      horizontal_label: "\udb82\udc4e"
      vertical_label: "\udb82\udc4f"
