# AbuLights 💡

Controlador de tiras LED Bluetooth (BLE) con interfaz gráfica para Windows.  
Conecta, controla colores, efectos y modos reactivos de audio/pantalla desde tu PC.

---

## Características

- Control de color RGB y brillo
- Efectos: Rainbow, Breathing, Strobe, Wave, Fade, Sunrise, Frost, Fire
- Modos reactivos: audio beat, color por audio, intensidad, color de pantalla, brillo de pantalla
- Tray icon — minimiza a la bandeja del sistema
- Detección automática del dispositivo si no se configura MAC/UUID

---

## Requisitos

- Windows 10/11
- Bluetooth activado
- Python 3.11 — https://www.python.org/downloads/release/python-3119/
- Dispositivo LED compatible (BJ_LED_M)

---

## Instalación

```bash
# 1. Clonar el repositorio
git clone https://github.com/tu-usuario/AbuLights.git
cd AbuLights

# 2. Crear entorno virtual
py -3.11 -m venv venv
source venv/Scripts/activate

# 3. Instalar dependencias
pip install -r requirements.txt
pip install numpy sounddevice Pillow
```

---

## Configuración

Copia `.env.example` a `.env` y edita con los datos de tu dispositivo:

```bash
cp .env.example .env
```

```env
LED_MAC_ADDRESS=XX:XX:XX:XX:XX:XX
LED_UUID=0000ee02-0000-1000-8000-00805f9b34fb
```

> Si los dejas vacíos, la app escanea y detecta el dispositivo automáticamente.

---

## Uso

**Opción A — Ejecutable (sin Python):**

```
Doble click en dist/AbuLights.exe
```

**Opción B — Desde código fuente:**

```bash
py -3.11 main.py
```

---

## Generar ejecutable

```bash
py -3.11 build_exe.py
```

El `.exe` quedará en `dist/AbuLights.exe`.

---

## Diagnóstico BLE

Si tienes problemas para conectar:

```bash
py -3.11 debug_ble.py
```

Escanea el dispositivo, lista servicios y UUIDs, e intenta escribir comandos para verificar la conexión.

---

## Estructura del proyecto

```
AbuLights/
├── abulights/        # Lógica BLE (manager, scanner)
├── gui/              # Interfaz gráfica PyQt6
├── src/ico/          # Assets (logo)
├── main.py           # Punto de entrada
├── build_exe.py      # Script para generar .exe
├── debug_ble.py      # Herramienta de diagnóstico
├── requirements.txt
└── .env.example
```

---

## Licencia

© 2026 ElAbuelo. All rights reserved.
