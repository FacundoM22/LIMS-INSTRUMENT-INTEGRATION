## 🔧 Integración Técnica entre el Instrumento Legacy y el Middleware (Lantronix)

Una vez definidos los componentes de hardware y software necesarios, esta sección describe **paso a paso** cómo se establece la comunicación entre la balanza Mettler Toledo Newclassic MS y el dispositivo de conversión serial a Ethernet, usando como middleware el **Lantronix UDS/EDS**.

### 4.1 Conexión Física

La balanza cuenta con un puerto **RS232C** (DB9) que debe conectarse directamente al **puerto serial del dispositivo Lantronix**.

- **Cable RS232 (DB9 macho-hembra):**
    - Tipo **directo** o **null-modem**, según el pinout de la balanza.
    - Verificar el manual técnico para confirmar configuración de pines y tipo de señal.
- **Cable Ethernet RJ45:**
    - Para conectar el Lantronix a la red local del laboratorio.

> 🧠 Se recomienda etiquetar los cables con el ID de la balanza y la IP asignada al Lantronix para facilitar el mantenimiento y la trazabilidad.

---

### 4.2 Configuración del Dispositivo Lantronix

La configuración se realiza a través de su **interfaz web incorporada**, accesible desde cualquier navegador conectado a la misma red.

#### Parámetros principales a configurar:

| Parámetro              | Valor típico / recomendado      | Comentario                                      |
|------------------------|----------------------------------|--------------------------------------------------|
| Baud rate              | 9600, 19200, etc.               | Debe coincidir con la balanza.                  |
| Bits de datos          | 7 u 8                           | Según modelo.                                   |
| Paridad                | None / Even / Odd               | Alineado con la configuración serie.            |
| Stop bits              | 1                               | Común en la mayoría de configuraciones.         |
| Control de flujo       | None / RTS/CTS / XON/XOFF       | Generalmente `None`, salvo excepciones.         |
| Modo de operación      | TCP Server                      | La PC cliente se conectará como cliente TCP.    |
| Puerto TCP             | 10001 (u otro configurable)     | A definir en función de la arquitectura.        |
| IP del dispositivo     | Fija (recomendada)              | Para evitar problemas con el DHCP.              |

---

### 4.3 Prueba de Conectividad

Una vez conectado y configurado el dispositivo:

1. Utilizar un software de terminal (ej: **Tera Term**, **RealTerm**, **Docklight**).
2. Establecer una conexión TCP/IP con la **IP y puerto del Lantronix**.
3. Enviar comandos (si la balanza los requiere, ej: `S` para solicitar peso).
4. Verificar que se reciba correctamente la trama, ej: `123.456 g\r\n`.

> 💡 Algunos modelos de balanza envían el peso automáticamente al estabilizarse. Otros requieren un comando de lectura explícito.

---

### 4.4 Consideraciones Adicionales

- **Tramas esperadas:** La estructura del dato suele incluir un valor numérico seguido de unidad (`g`) y un terminador como `CR/LF`. Ejemplo: `124.980 g\r\n`
- **Ruido eléctrico:** Se recomienda una fuente de alimentación estabilizada y uso de cables blindados si hay interferencia.
- **IP fija:** Asignar manualmente la IP al Lantronix o usar una reserva en DHCP para garantizar estabilidad.
- **Nombre lógico:** Si el dispositivo será consumido por múltiples clientes, puede ser útil asociar la IP a un nombre lógico en el DNS local (ej: `balanza-pesajes.lab.local`).

---

Esta configuración convierte la balanza en un **dispositivo de red accesible**, con posibilidad de ser consumido por aplicaciones externas o middleware que puedan interpretar y direccionar los datos hacia un sistema LIMS.
