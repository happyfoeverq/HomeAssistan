# HomeAssistan

## 斐讯M1传感器离线插件修改版
适用于 HA Core 2025.1之后版本，原出处见https://bbs.hassbian.com/thread-4952-1-1.html

参考配置文件（112233445566为斐讯M1的MAC地址）
```yaml
sensor:
  - platform: aircat #斐讯M1传感器
    name: m1
    mac: {'112233445566':'brightness_m1a'}
    brightness_force_update: True

input_select:
  brightness_m1a: #斐讯M1传感器亮度调节
    name: 斐讯M1亮度
    options:
      - 关闭
      - 夜间
      - 白天

group:
  m1a:
    name: 客厅M1
    entities:
      - sensor.m1_hcho
      - sensor.m1_humidity
      - sensor.m1_pm2_5
      - sensor.m1_temperature
      - input_select.brightness_m1a

homeassistant:
  customize:
    sensor.m1_hcho:
      icon: mdi:chemical-weapon
      device_class: hcho 
      friendly_name: 甲醛
    sensor.m1_humidity:
      icon: mdi:water-percent
      device_class: humidity 
      friendly_name: 湿度 
    sensor.m1_pm2_5:
      icon: mdi:blur
      device_class: pm25 
      friendly_name: 空气质量
    sensor.m1_temperature:
      #icon: mdi:    
      device_class: temperature
      friendly_name: 温度      

```
