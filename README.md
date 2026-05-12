# 💬 Chat Híbrido TCP/UDP en Java

> Proyecto Final · Redes de Computadoras · ITSON

Aplicación de chat cliente-servidor desarrollada en Java que permite comunicación en tiempo real mediante **TCP** y **UDP** simultáneamente.

---

## 📋 Descripción

Este proyecto consiste en un servidor híbrido capaz de atender clientes tanto por **TCP** (conexión orientada a flujo) como por **UDP** (sin conexión). Los clientes pueden registrarse con un nombre de usuario válido y enviar mensajes grupales o privados. El servidor gestiona la concurrencia mediante hilos y controla la inactividad de los usuarios.

---

## 👥 Integrantes

| Nombre                      | Matrícula    |
|-----------------------------|--------------|
| Felix isaac Sanchez Quintero| 00000244737  |
| Armando Rayos               | 00000133634  |

---

## 🛠️ Tecnologías utilizadas

- **Java 17+**
- **Sockets TCP** (`Socket` / `ServerSocket`)
- **Sockets UDP** (`DatagramSocket` / `DatagramPacket`)
- **Multihilos** (`Thread`)
- **NetBeans IDE**
- Manejo de flujos con `BufferedReader` y `PrintWriter`

---

## 📁 Estructura del proyecto

```
Chat-Hibrido-TCP-UDP/
├── src/
│   ├── client/
│   │   └── Cliente.java                 # Cliente TCP y UDP
│   ├── server/
│   │   └── ServidorHibrido.java         # Servidor principal (TCP + UDP)
│   └── Main.java (opcional)
├── build/
├── dist/
├── screenshots/
│   ├── servidor-activo.png
│   ├── cliente-tcp.png
│   ├── cliente-udp.png
│   ├── mensaje-privado.png
│   └── usuarios-conectados.png
└── README.md
```

---

## 🚀 Cómo ejecutar

### 1. Iniciar el Servidor

Abre el proyecto en **NetBeans**, compila y ejecuta la clase:

```bash
ServidorHibrido.java
```
Si no tienes neatbeans Puedes descargar desde el siguiente link: 
https://archive.apache.org/dist/netbeans/netbeans-installers/23/Apache-NetBeans-23-bin-windows-x64.exe

luego acepta todos los terminos , luego procura descargar la carpeta de **Chat-TCP-UDP**, luego abres neatbeans te vas a la parte de files y abrir abrir proyecto:
<img width="1289" height="763" alt="image" src="https://github.com/user-attachments/assets/68cbacd6-0d64-401a-ae8e-f61a9cb143e3" />

luego buscas donde guardaste la carpeta donde se encuentra el projecto:
<img width="237" height="21" alt="image" src="https://github.com/user-attachments/assets/162e420b-8727-421c-b0c9-ae6ce7d41671" />
cuando se abra el proyecto con click derecho y te vas a la parte de Run y listo ya puedes correr el proyecto con exito:
<img width="312" height="285" alt="image" src="https://github.com/user-attachments/assets/45bcc90c-76a2-4e0a-a11b-e33ec9b03728" />



O desde terminal vete al buscador de windows y buscas **Terminal** y copias y pagas los siguientes comandos :
```bash
javac -d bin src/server/ServidorHibrido.java
java -cp bin server.ServidorHibrido
```
o sino tambien con las teclas Win + R te abrira el ejecutor y despues pon la palabra CDM , le das enter y listo ya solo es copiar y pegar los comandos en la teminal: 
<img width="392" height="195" alt="image" src="https://github.com/user-attachments/assets/c1a64aa0-125a-4a16-9079-b123697d3d46" />



El servidor te pedirá el puerto (recomendado: `5000`).

### 2. Iniciar Cliente(s)

Ejecuta la clase `Cliente.java` tantas veces como clientes desees.

Cada cliente podrá elegir entre **TCP** o **UDP**.

---

## ⚙️ Funcionalidades implementadas

- [x] Soporte simultáneo de clientes **TCP** y **UDP**
- [x] Registro de usuario con validación estricta
- [x] Validación de nombres: letras, números, `_`, `-` y `.`
- [x] Mensajes grupales (broadcast)
- [x] Mensajes privados (`/priv nombre mensaje`)
- [x] Detección de inactividad (Heartbeat + Timeout)
- [x] Límite máximo de usuarios (5)
- [x] Comando `exit` para desconexión controlada
- [x] Manejo de errores y respuestas claras

---

## 📊 Diagramas de Arquitectura

### Diagrama del Servidor
<img width="3840" height="2160" alt="diagramasdiagrama servidor@2x-100 jpg" src="https://github.com/user-attachments/assets/56b4413c-1351-4960-93a6-1532d0f968fd" />


### Diagrama del Cliente
<img width="3840" height="2161" alt="diagramasdiagrama cliente@2x-100 jpg" src="https://github.com/user-attachments/assets/0d297580-e79e-440b-87ec-ceee2b9aaeb4" />


---

## 🏗️ Arquitectura General

El sistema está diseñado con una arquitectura **híbrida** (TCP + UDP), donde:

- El servidor maneja conexiones TCP y UDP en el **mismo puerto**.
- Cada cliente TCP tiene su propio hilo.
- Los clientes UDP se identifican por (IP:Port).
- Se utiliza un sistema de heartbeat + timeout para detectar inactividad.


---
## 📸 Capturas de pantalla


- Servidor activo
<img width="1444" height="520" alt="Captura de pantalla 2026-05-10 191039" src="https://github.com/user-attachments/assets/f6052f84-7cde-4e0c-a578-6bd2c58f7dfe" />

- Cliente TCP conectado
                     - Primera captura vista desde la clase Usario:
- <img width="1784" height="632" alt="Cliente TCP conectado-PovCliente" src="https://github.com/user-attachments/assets/8562b859-729b-4b70-9bf4-a8229f147d10" />

                      - Segunda Captura Perspectiva del Servidor:
<img width="1686" height="629" alt="Cliente TCP conectado-PovServidorHibrido" src="https://github.com/user-attachments/assets/fa2666c4-b74e-41b6-9f16-34cbcb003d6d" />

  
- Cliente UDP conectado
                   - Primera captura vista desde la clase Usario:
  <img width="1686" height="617" alt="Captura de pantalla 2026-05-10 184949" src="https://github.com/user-attachments/assets/7cb7bc6b-cb13-4c3a-9233-2f321f939dd6" />

                    - Segunda Captura Perspectiva del Servidor:
  <img width="1670" height="600" alt="Captura de pantalla 2026-05-10 185133" src="https://github.com/user-attachments/assets/d110225d-6916-42b1-8146-35f6b1881741" />

                  
- Mensaje privado
                  - Primera captura vista desde la clase Usario Felix y Maria:
                    <img width="1180" height="626" alt="Captura de pantalla 2026-05-10 190536" src="https://github.com/user-attachments/assets/81fea674-0a19-4019-992f-995998b35c08" />

                    <img width="831" height="630" alt="Captura de pantalla 2026-05-10 190600" src="https://github.com/user-attachments/assets/8ea7c117-8b85-471a-aef0-1bb6a7896f27" />

                -  Segunda perspectiva desde la clase Usuario pero siendo el 3er Usuario creado:
  <img width="850" height="637" alt="Captura de pantalla 2026-05-10 190727" src="https://github.com/user-attachments/assets/09514bc6-48f3-40cf-b247-9245b40eacc6" />



- 
- Múltiples usuarios
<img width="992" height="637" alt="Captura de pantalla 2026-05-10 190943" src="https://github.com/user-attachments/assets/6ea793b0-b559-42cb-af7b-b70820b428d8" />

---

## 🔧 Reglas de nombres de usuario

Los nombres deben cumplir con el siguiente formato:
- Solo se permiten: **letras (A-Z, a-z)**, **números (0-9)**, **guion bajo (_)**, **guion medio (-)** y **punto (.)**
- No se permiten espacios ni caracteres especiales

---

## 📄 Notas del proyecto

- El servidor utiliza un solo puerto para aceptar tanto conexiones TCP como paquetes UDP.
- Se implementó un sistema de limpieza automática de usuarios inactivos (20 segundos).
- El código está preparado para ser fácilmente extensible (GUI, base de datos, etc.).

---

## 🌐 Protocolo de comunicación

- **TCP**: Usa flujos de texto (`PrintWriter` / `BufferedReader`)
- **UDP**: Usa datagramas con comandos (`JOIN:`, `HEARTBEAT`, `:exit`, etc.)

---

**Proyecto desarrollado para la materia de Redes de Computadoras - ITSON 2026**

