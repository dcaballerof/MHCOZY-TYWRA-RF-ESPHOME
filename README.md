# MHCOZY-TYWRA-RF-ESPHOME

<img width="640" height="640" alt="image" src="https://github.com/user-attachments/assets/07f8b658-b1db-45c3-9920-e291f8fc2ffc" />

Flasheo y configuración con Esphome (HAOS)

Lo primero es localizar los pines para usar un conversor USB-TTL (los he marcado con amarillo)
<img width="836" height="557" alt="image" src="https://github.com/user-attachments/assets/1ebcef71-96c4-4b21-a06d-f8338a2504ec" />

<img width="293" height="469" alt="image" src="https://github.com/user-attachments/assets/f5328be5-576d-41d3-ba99-c5c4708f856e" />


Para el modo BOOT vamos a hacer puente en el momento del flasheo entre CEN y GND.

Con ESPHOME hacemos el código YAML que adjunto en el post.

Y tenemos que generar el archivo para la app Itchiptool, en la cual vamos a flashear subiendo el archivo que nos da EspHome (previamente le hemos dado de alta, es un BK72XX y después seleccionas CB3S WIFI MODULE:

<img width="307" height="410" alt="image" src="https://github.com/user-attachments/assets/5eb16558-4724-4ae3-bc4b-bae832182b29" />


<img width="550" height="424" alt="image" src="https://github.com/user-attachments/assets/055a6977-3d70-4c26-a3d7-b94223075a35" />

Y listo, cuando todo esté ok, en EspHome aparecera Online... ya puedes volcar datos con OTA desde ahí, y recuerda generar en Configuración/Dispositivos y Servicios/EspHome/nuevo el dispositivo con la IP que le pongas... 

<img width="523" height="178" alt="image" src="https://github.com/user-attachments/assets/b8b3f768-9b22-4e88-bbd4-a80164e8e19d" />

<img width="1054" height="179" alt="image" src="https://github.com/user-attachments/assets/d08df48b-60b8-4f45-bd2b-fe99fcfe6d5b" />

<img width="1045" height="731" alt="image" src="https://github.com/user-attachments/assets/f2c1d020-4d28-4171-90db-bc739ef05e98" />







