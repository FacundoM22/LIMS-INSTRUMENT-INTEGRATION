# ⚙️ Mantener un sistema híbrido con splitters RS232

A veces la integración no puede ser **100% digital** ni **100% manual**.  
En este caso, el laboratorio necesitaba seguir usando la impresora térmica original **y** al mismo tiempo enviar los datos al LIMS.  

La solución fue armar un sistema híbrido usando **splitters RS232**, para duplicar la señal y mandarla tanto al middleware como a la impresora.

---

## 🎯 El desafío real
El problema no era solo “conectar el splitter y listo”.  
Había que asegurarse de que la señal fuera estable en ambas salidas, sin pérdidas ni errores raros.  
Y encima, había que coordinar que todos hablaran el mismo idioma: **baud rate**, paridad, bits de datos y bits de stop perfectamente alineados.  

Un paso mal y la impresora o el LIMS empezaban a quejarse.

---

💡 _Más adelante voy a sumar_:  
- El esquema de cableado que funcionó mejor  
- Los modelos de splitters que dieron buenos resultados  
- Y los que es mejor evitar
