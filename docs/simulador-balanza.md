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

<p align="center">
  <img src="files/Simulador de balanza PIC/Icon.PNG" alt="Icono del simulador de balanza." width="100"/>
</p>


## 🧭 Paso 1: Iniciar el servidor en el Simulador de Balanza

El primer paso para comenzar la simulación es iniciar el servidor TCP desde la interfaz del simulador. Esto habilita la escucha en el puerto 9000, esperando una conexión desde un cliente (como Hercules o un sistema LIMS).

<p align="center">
  <img src="files/Simulador de balanza PIC/Simulador de balanza TCP connect.PNG" alt="Iniciar servidor TCP en el Simulador de Balanza" width="600"/>
</p>

> ✅ Una vez iniciado, el log indicará que el simulador está escuchando conexiones entrantes.


## 🔗 Paso 2: Conexión desde el cliente (Hercules)

Una vez que el servidor TCP del simulador está activo, se puede establecer la conexión desde un cliente como **Hercules**. En este caso, se realiza la conexión a `127.0.0.1:9000`, que corresponde al localhost (misma PC).

<p align="center">
  <img src="files/Simulador de balanza PIC/Secuencia automatica.PNG" alt="Ejemplo de peso enviado al LIMS" width="1000"/>
</p>

> ✅ Hercules confirma la conexión exitosa mostrando el estado de conexión activa. A partir de este punto, está preparado para recibir los datos de peso simulados.

## ⏹️ Paso 3: Detener el servidor del simulador

Cuando finalices las pruebas, es importante detener correctamente el servidor TCP para liberar el puerto y cerrar la conexión.

<p align="center">
  <img src="files/Simulador de balanza PIC/Servidor detenido.PNG" alt="Servidor detenido en el simulador de balanza" width="1000"/>
</p>

> 🔌 Al hacer clic en "Detener Servidor", el simulador cerrará la conexión y dejará de escuchar nuevos clientes.

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

