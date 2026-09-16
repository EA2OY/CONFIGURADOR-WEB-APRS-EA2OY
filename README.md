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

### 💾 Los binarios de `uf2/`, con fecha y SHA-256

> ✅ **Cada binario dice lo que lleva (contador de compilación arreglado el 2026-09-16)**: el
> número sube **cuando cambia el código**, así que el que contesta el nodo por USB
> (`1.0alpha b13`) identifica el firmware, y coincide con el nombre del fichero. Hasta esa noche
> el contador estuvo clavado en `b9` (un fallo del propio contador), así que **si tienes
> descargado un `..._b9_...`, es el mismo firmware que el `b13` con el número viejo**. La fecha y
> el **SHA-256** de esta tabla sirven para comprobar lo que te has bajado (los seis de [`uf2/`](uf2)):

| Fichero | Fecha | Bytes | SHA-256 |
|---|---|---|---|
| `KachoSystem_v1.0alpha_b13_Faketec_HT-RA62_433.uf2` | 2026-09-16 | 749568 | `0B9E1FE9E52974EEDAB852E35CF2F17FF90AF4D91D28CB2B82DAA828604F097A` |
| `KachoSystem_v1.0alpha_b13_Faketec_E22P-433M30S.uf2` | 2026-09-16 | 749568 | `B65B79A3596B1906AE16AEC51FEEC1C1C57D162169CF294B1D61450C6DDFE69F` |
| `KachoSystem_v1.0alpha_b13_LilyGO_T-Echo_S140v7.uf2` | 2026-09-16 | 743424 | `31148799C9140770AC33BF861F96868C38B29739C251FED5237A0A2F928ADB2D` |
| `KachoSystem_v1.0alpha_b13_LilyGO_T-Echo-Plus_S140v7.uf2` | 2026-09-16 | 740352 | `1F8763492C799DCB3C0F4B7FEAACC6A710CD3B062BE3C9BDE641155F3615F65E` |
| `KachoSystem_v1.0alpha_b3_LilyGO_T-Echo.uf2` | 2026-09-14 | 599552 | `5F06A6F660D24F62BD8FF539FEEB08291EBE7E64C67E0FEA5C4DB18CB8661E78` |
| `KachoSystem_v1.0alpha_b3_LilyGO_T-Echo-Plus.uf2` | 2026-09-14 | 599552 | `E7A121F0442A8500617B335F3432340C8DB39E135DBC3F35961035B8AF903B3F` |

Las cuatro filas **b13** se recompilaron el **2026-09-16** desde el código de
[EA2OY/EA2OY-APRS-SYSTEM](https://github.com/EA2OY/EA2OY-APRS-SYSTEM); las dos **b3** son del
**2026-09-14** y se dejan tal cual (son las que van en un T-Echo con cargador de arranque S140
**versión 6**, para el que no hay build b13). Para comprobar la huella en tu ordenador (Windows,
PowerShell): `Get-FileHash .\KachoSystem_v1.0alpha_b13_LilyGO_T-Echo_S140v7.uf2 -Algorithm SHA256`

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
