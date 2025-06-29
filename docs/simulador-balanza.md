# ⚖️ Simulador Virtual de Balanza Analítica - Versión Ejecutable

Este simulador permite emular el comportamiento de una balanza analítica conectada por red TCP/IP. Es ideal para **pruebas de integración** en laboratorios que aún no cuentan con el hardware físico (como el conversor Lantronix) pero necesitan validar la comunicación con el sistema LIMS.

---

## 📥 Descarga

Descargá el ejecutable para Windows desde el siguiente enlace:

[⬇️ Descargar simulador_balanza.exe](https://github.com/tuusuario/tu-repo/releases/download/v1.0/simulador_balanza.exe)

> 🔐 **Nota:** Algunos antivirus pueden generar falsos positivos debido a que el ejecutable fue empaquetado con PyInstaller. Podés verificar su seguridad en [VirusTotal](https://www.virustotal.com/gui/file/TU_HASH_AQUI).  
> El código fuente está disponible en este mismo repositorio para mayor transparencia.

---

## 🖥️ Interfaz del Simulador

A continuación se muestran capturas reales de la interfaz de la balanza virtual:

<p align="center">
  <img src="files/Simulador de balanza PIC/Icon.PNG" alt="Icono del simulador de balanza." width="100"/>
</p>

<p align="center">
  <img src="files/Simulador de balanza PIC/Secuencia automatica.PNG" alt="Ejemplo de peso enviado al LIMS" width="1000"/>
</p>


<p align="center">
  <img src="files/Simulador de balanza PIC/Simulador de balanza TCP connect.PNG" alt="Ejemplo de peso enviado al LIMS" width="600"/>
</p>


<p align="center">
  <img src="files/Simulador de balanza PIC/Servidor detenido.PNG" alt="Ejemplo de peso enviado al LIMS" width="1000"/>
</p>



---

## ⚙️ Funcionalidades

| Función                          | Descripción |
|----------------------------------|-------------|
| **Iniciar servidor**             | Abre un socket TCP (por defecto en el puerto `9000`) y espera conexiones. |
| **Enviar peso fijo**             | Envía un valor manual ingresado (ej: `5.000 g`) al cliente conectado. |
| **Enviar peso aleatorio**        | Genera y envía un valor entre 0.001 g y 250.000 g. |
| **Secuencia automática**         | Envia pesos aleatorios cada segundo hasta que se detenga. |
| **Log de eventos**               | Muestra en tiempo real todas las conexiones y pesos transmitidos. |

---

## 🧪 Cómo integrarlo con un cliente TCP (como Hercules)

1. Abrí Hercules.
2. En la pestaña **TCP Client**, conectate a `127.0.0.1` en el puerto `9000`.
3. Desde el simulador, iniciá el servidor.
4. Probá enviar pesos fijos o aleatorios, y verás los datos reflejados en Hercules.

<p align="center">
  <img src="images/hercules_recibiendo.png" alt="Hercules mostrando datos enviados por la balanza virtual" width="600"/>
</p>

---

## 💡 Casos de uso

- Validar una integración LIMS antes de tener el hardware.
- Simular comportamiento de una balanza real en una red TCP.
- Crear scripts de testing para la capa software sin necesidad de laboratorio físico.


---

## 🔐 Seguridad y transparencia

El simulador fue construido con **Python 3.13** y empaquetado usando **PyInstaller**. Debido a este empaquetado, algunos antivirus pueden lanzar advertencias **falsas**.

🧪 Ver análisis en: [VirusTotal](https://www.virustotal.com/gui/file/7d13f449ddb1d66fbbcb5b7a3a2f82b0f6cce230401dc0edcf87b60127cbdafe)

---

## 📬 Contacto

Para reportar errores o sugerencias:  
✉️ facundomoriconi.code@gmail.com

---

© 2025 - Proyecto educativo y de integración en laboratorios. Distribución libre bajo licencia MIT.

