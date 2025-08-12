   En este caso, la integración no podía ser “todo digital” ni “todo manual”: el laboratorio necesitaba seguir utilizando la impresora térmica original y al mismo tiempo enviar los datos al LIMS.
   La solución fue implementar un sistema híbrido mediante splitters RS232, que permiten duplicar la señal para que viaje tanto al middleware como al dispositivo de impresión.
   
   El desafío real no fue solo conectar el splitter, sino garantizar que la señal se mantuviera estable en ambas salidas sin pérdidas, errores de transmisión o interferencias. Además, hubo que coordinar las configuraciones de baud rate y paridad para que tanto la impresora como el sistema LIMS “hablaran el mismo idioma” sin que ninguno de los dos se quejara.
   
   💡 Más adelante voy a documentar el esquema de cableado, los modelos de splitters que funcionaron mejor y los que fue mejor evitar.
