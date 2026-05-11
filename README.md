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
| Armando Rayos        | id           |

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

O desde terminal:
```bash
javac -d bin src/server/ServidorHibrido.java
java -cp bin server.ServidorHibrido
```

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

## 📸 Capturas de pantalla

*(Agrega aquí tus capturas)*

- Servidor activo
- Cliente TCP conectado
                     - Primera captura vista desde la clase Usario:
- <img width="1784" height="632" alt="Cliente TCP conectado-PovCliente" src="https://github.com/user-attachments/assets/8562b859-729b-4b70-9bf4-a8229f147d10" />

                      - Segunda Captura Perspectiva del Servidor:
<img width="1686" height="629" alt="Cliente TCP conectado-PovServidorHibrido" src="https://github.com/user-attachments/assets/fa2666c4-b74e-41b6-9f16-34cbcb003d6d" />

  
- Cliente UDP conectado
- Mensaje privado
- Múltiples usuarios

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

