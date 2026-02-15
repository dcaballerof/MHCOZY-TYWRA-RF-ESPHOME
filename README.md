# MHCOZY-TYWRA-RF-ESPHOME
Flasheo y configuración con Esphome (HAOS)

Lo primero es localizar los pines para usar un conversor USB-TTL (los he marcado con amarillo)
<img width="836" height="557" alt="image" src="https://github.com/user-attachments/assets/1ebcef71-96c4-4b21-a06d-f8338a2504ec" />

<img width="293" height="469" alt="image" src="https://github.com/user-attachments/assets/f5328be5-576d-41d3-ba99-c5c4708f856e" />


Para el modo BOOT vamos a hacer puente en el momento del flasheo entre CEN y GND.

Con ESPHOME hacemos el código YAML, adjunto: 

esphome:
  name: pon el tuyo
  friendly_name: pon el tuyo

bk72xx:
  board: cb3s

# Enable logging
logger:

# Enable Home Assistant API
api:
  encryption:
    key: "pon el tuyo"

ota:
  - platform: esphome
    password: "pon el tuyo"

wifi:
  ssid: !secret wifi_ssid
  password: !secret wifi_password
  manual_ip:
    static_ip: 192.168.x.x
    gateway: 192.168.x.x
    subnet: 255.255.255.0
    
  # Enable fallback hotspot (captive portal) in case wifi connection fails
  ap:
    ssid: "pon el tuyo"
    password: "pon el tuyo"

captive_portal:
    
binary_sensor:
  - platform: gpio
    pin:
      number: P6
      inverted: true
      mode: INPUT_PULLUP
    name: "Botón físico"
    filters:
      - delayed_on: 50ms
      - delayed_off: 50ms
    on_press:
      - switch.toggle: relay_1

# -------------------
# RF 433 MHz (P14)
# -------------------
  - platform: gpio
    pin:
      number: P14
      inverted: true
      mode: INPUT_PULLUP
    name: "RF 433"
    filters:
      - delayed_on: 50ms
      - delayed_off: 50ms
    on_press:
      - switch.toggle: relay_1

# -------------------
# RELÉ (P24)
# -------------------
switch:
  - platform: gpio
    name: "Relé"
    id: relay_1
    pin:
      number: P24
      inverted: false
    restore_mode: ALWAYS_OFF
    on_turn_on:
      - output.turn_on: led_azul
    on_turn_off:
      - output.turn_off: led_azul

# -------------------
# LED (P8 - activo en LOW)
# -------------------
output:
  - platform: gpio
    id: led_azul
    pin:
      number: P8
      inverted: true

Y tenemos que generar el archivo para la app Itchiptool, en la cual vamos a flashear subiendo el archivo que nos da EspHome.

<img width="550" height="424" alt="image" src="https://github.com/user-attachments/assets/055a6977-3d70-4c26-a3d7-b94223075a35" />

Y listo, cuando todo esté ok, en EspHome aparecera Online... ya puedes volcar datos con OTA desde ahí, y recuerda generar en Configuración/Dispositivos y Servicios/EspHome/nuevo el dispositivo con la IP que le pongas... 

<img width="523" height="178" alt="image" src="https://github.com/user-attachments/assets/b8b3f768-9b22-4e88-bbd4-a80164e8e19d" />

<img width="1054" height="179" alt="image" src="https://github.com/user-attachments/assets/d08df48b-60b8-4f45-bd2b-fe99fcfe6d5b" />

<img width="1045" height="731" alt="image" src="https://github.com/user-attachments/assets/f2c1d020-4d28-4171-90db-bc739ef05e98" />







