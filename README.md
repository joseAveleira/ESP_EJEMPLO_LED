# Proyecto: Control de LED con Sensor Táctil Capacitivo

Este proyecto utiliza un ESP32 para controlar un LED mediante un sensor táctil capacitivo. El código implementa un sistema simple en el que al tocar el pin capacitivo asignado, se alterna el estado del LED (encendido o apagado). Además, se muestra el estado actual del LED en el monitor serie.

## Características del Proyecto

- **Microcontrolador**: ESP32.
- **Control táctil**: Usa la capacidad de detección táctil integrada del ESP32.
- **Indicador LED**: Utiliza el LED interno del ESP32 como indicador visual.
- **Monitor Serie**: Muestra el estado actual del LED en tiempo real.
- **Debounce por software**: Incluye un retraso para evitar múltiples activaciones por un solo toque.

## Esquema de Conexión

- **TOUCH_PIN (GPIO 32)**: Pin táctil capacitivo.
- **LED_PIN (GPIO 2)**: Pin conectado al LED interno del ESP32.

## Funcionamiento del Código

1. **Inicialización**:
   - Configura el pin del LED como salida.
   - Inicia la comunicación por el puerto serie a una velocidad de 115200 baud.

2. **Detección Táctil**:
   - Se lee el valor del sensor táctil capacitivo.
   - Si el valor leído es menor a 20 (indicando un toque), el estado del LED cambia (encendido/apagado).

3. **Control del LED**:
   - El estado del LED se actualiza usando el pin GPIO 2.
   - Se muestra en el monitor serie si el LED está `ENCENDIDO` o `APAGADO`.

4. **Debounce por Software**:
   - Se aplica un retraso de 600 ms después de cada detección de toque para evitar múltiples activaciones.

## Código Fuente

El código fuente está incluido en este repositorio. Puedes encontrarlo en el archivo `main.ino`.

## Cómo Usar

1. **Requisitos**:
   - Un ESP32.
   - Arduino IDE configurado con la placa ESP32.
   - Cable micro-USB para cargar el programa al ESP32.

2. **Configuración del Proyecto**:
   - Clona este repositorio o descarga los archivos.
   - Abre el archivo `main.ino` en Arduino IDE.

3. **Subir el Código**:
   - Selecciona la placa ESP32 y el puerto correcto en Arduino IDE.
   - Carga el código al ESP32.

4. **Pruebas**:
   - Abre el monitor serie en Arduino IDE (115200 baud).
   - Toca el pin capacitivo (GPIO 32) y observa el cambio en el LED y el monitor serie.

## Ejemplo de Salida en el Monitor Serie

```plaintext
Estado del LED: ENCENDIDO
Estado del LED: APAGADO
Estado del LED: ENCENDIDO
