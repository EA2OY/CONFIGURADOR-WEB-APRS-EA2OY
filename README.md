<div align="center">

<img src="https://raw.githubusercontent.com/EA2OY/EA2OY-APRS-SYSTEM/main/assets/logo_kacho.svg" alt="Kacho System" width="150">

# ⚙️ Configurador web — Kacho System

### Nodos APRS-LoRa de 433 MHz (nRF52840) — Faketec y LilyGO T-Echo

*No es una captura ni una maqueta: es **el configurador real**, servido como página web para que
puedas conectar tu nodo por USB y configurarlo desde el navegador.* 📡

</div>

---

## 🚀 Pruébalo ahora

<p align="center">
  <a href="https://ea2oy.github.io/CONFIGURADOR-WEB-APRS-EA2OY/" target="_blank" rel="noopener">
    <strong>👉 Abrir el configurador online ⚙️</strong>
  </a>
</p>

| Paso | Qué hacer |
|---|---|
| 1️⃣ | Abre el enlace de arriba con **Chrome o Edge** en un **ordenador** |
| 2️⃣ | Enchufa tu nodo por **USB** |
| 3️⃣ | Pulsa **Conectar** y elige el puerto del nodo |
| 4️⃣ | La página **lee la configuración real** del aparato y rellena el formulario |
| 5️⃣ | Cambia lo que necesites y pulsa **Guardar**: la respuesta enseña **los valores que el nodo ha aceptado** |

> 🖥️ **Hace falta un ordenador.** WebSerial (lo que permite hablar con el nodo por USB) **no
> existe** en Firefox, Safari ni en el navegador del móvil. Desde el móvil puedes abrir la página,
> pero no conectar con el nodo.

## ✨ ¿Qué se puede hacer desde aquí?

| | |
|---|---|
| 📊 **Estado en vivo** | Lo que está haciendo el nodo ahora mismo, y consola de lo que dice |
| 🎛️ **Configuración completa** | Indicativo, coordenadas, modo (repetidor / rastreador / ambos), rutas y saltos, cadencias de baliza, radio (frecuencia, velocidad, ancho de banda, potencia), sensores, pantalla, energía y control remoto |
| 🧭 **Perfiles de uso** | Los cuatro perfiles (fijo, a pie, bici y coche) se editan en una tabla: **SSID**, cadencia **lenta** y **rápida**, **cada cuántos metros** y el **icono** con el que sales en el mapa |
| 🕹️ **Acciones** | Mandar baliza, telemetría, leer estado, silenciar, reiniciar, volver a valores de origen, borrado total y modo grabación |
| ✉️ **Mensajes APRS** | Mensajes a otra estación, boletines (`BLN0`-`BLN9`) y objetos |
| 🗺️ **Registro de viaje** | Descargar lo que el nodo guardó, **verlo en un mapa** y exportar a **GPX, KML o CSV** |
| ❓ **Ayuda en cada casilla** | Un botón «?» explica cada ajuste en lenguaje claro, en español y en inglés |
| ⚠️ **Avisos de radioaficionado** | Te dice lo que conviene saber antes de guardar (por ejemplo, si pides demasiados saltos para un nodo fijo) — **avisa, no impide guardar** |

## 🔒 Sobre tu indicativo

**El firmware no trae ningún indicativo grabado.** La configuración vive en el propio nodo y la
pones tú desde aquí: cada aparato se identifica con **la llamada de su dueño**. Esta página no
guarda nada tuyo: es solo la herramienta que habla con tu nodo.

## ⚠️ Qué NO hace

| Límite | Por qué |
|---|---|
| ❌ **Configurar desde el móvil** | WebSerial solo existe en navegador de escritorio (Chrome/Edge) |
| ❌ **Guardar tu configuración en la nube** | Todo va directo del navegador a tu nodo por USB; aquí no se guarda nada |
| ❌ **Funcionar sin el nodo enchufado** | Es el configurador *de un aparato*: sin nodo no hay nada que configurar |
| ❌ **Cambiar la radio al instante** | Frecuencia, velocidad, ancho de banda y potencia **necesitan reiniciar** el nodo (la página te avisa) |

## 🗺️ El mapa del recorrido

Al leer el registro de viaje, la ruta se dibuja **en un mapa propio, sin librerías de internet**:
se arrastra, la rueda acerca, hay botones **+ / −** y **«Ajustar a la ruta»**, y el principio y el
final van marcados con **A** y **B**. Debajo sale un resumen: puntos, distancia, velocidad máxima,
altitud mínima y máxima, y duración.

> **¿Por qué se sirve como página web y no como fichero suelto?** Por dos motivos muy concretos:
> 1. **WebSerial solo funciona en un sitio seguro** (`https://` o `http://localhost`). Abierto como
>    fichero, el navegador no deja hablar con el USB.
> 2. **El mapa necesita una dirección web de verdad**: el servidor de teselas de OpenStreetMap
>    **exige** que las peticiones lleven cabecera `Referer` y **prohíbe el uso sin conexión**. Su
>    política no se debe burlar; sirviendo la página por web, funciona como es debido.

*(Sin conexión, la ruta se sigue viendo sobre un fondo con rejilla: el mapa avisa y hay un botón
«Sin fotos» para ahorrar datos.)*

## 📁 Qué hay en este repositorio

| Fichero | Qué es |
|---|---|
| [`configurador.html`](configurador.html) | **El configurador entero, en un solo fichero y sin dependencias** |
| [`index.html`](index.html) | Portada que lleva al configurador, al manual y al firmware |
| [`flasher.html`](flasher.html) | Guía para grabar el firmware en un nodo, con comprobación del estado de la placa |
| [`uf2/`](uf2) | Los ficheros de firmware listos para copiar a la placa (uno por placa), con el número de compilación en el nombre |
| [`Manual_Kacho_System.pdf`](Manual_Kacho_System.pdf) | El manual de uso, para tenerlo a mano |
| [`README_configurador.md`](README_configurador.md) | Notas del configurador y sus comprobadores |

## 📘 Documentación y firmware

| | |
|---|---|
| 📕 **Manual de uso (PDF)** | [`Manual_Kacho_System.pdf`](Manual_Kacho_System.pdf) — los perfiles de uso, capítulo **«Los perfiles de uso»** |
| 📄 Manual en texto | [MANUAL_USUARIO.md](https://github.com/EA2OY/EA2OY-APRS-SYSTEM/blob/main/MANUAL_USUARIO.md) |
| 💾 **Firmware y código fuente** | [EA2OY/EA2OY-APRS-SYSTEM](https://github.com/EA2OY/EA2OY-APRS-SYSTEM) |
| 📡 Firmware compilado listo para grabar | [firmware/release](https://github.com/EA2OY/EA2OY-APRS-SYSTEM/tree/main/firmware/release) |
| 🔧 Documentación técnica | [docs/](https://github.com/EA2OY/EA2OY-APRS-SYSTEM/tree/main/docs) |

## 📜 Licencia

**GPL-3.0**, igual que el firmware del que forma parte.

---

<div align="center">

**Hecho con ❤️ y mucho café por Kacho (EA2OY)**

*Nodos APRS-LoRa de 433 MHz · repetidor y rastreador*

</div>
