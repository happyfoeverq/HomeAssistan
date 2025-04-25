# HomeAssistan

斐讯M1传感器离线插件修改版，适用于 HA Core 2025.1之后版本，原出处见https://bbs.hassbian.com/thread-4952-1-1.html
参考配置文件：

sensor:
  - platform: aircat #斐讯M1传感器
    name: m1
    mac: {'B0F8932396ED':'brightness_m1a'}
    brightness_force_update: True

input_select:
  brightness_m1a: #斐讯M1传感器亮度调节
    name: 斐讯M1亮度
    options:
      - 关闭
      - 夜间
      - 白天
