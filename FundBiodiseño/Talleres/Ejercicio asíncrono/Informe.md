## Informe del Ejercicio Asíncrono
* ### Esquema de Conexión:
```text
        3.3 V
          |
          |
     Flex sensor
          |
          |
          +-------> ADC (GPIO36 en la guía original)
          |
          |
        47 kΩ
          |
          |
         GND
```
![Fotos conexión](https://github.com/PaoloCustodio/EQUIPO-12/blob/6ded9de0abe0de241aaf30a24beabb8a42ff447f/Recursos%20e%20im%C3%A1genes/WhatsApp%20Image%202026-10-07%20at%208.45.01%20AM.jpeg)

* ### Tabla de calibración de datos reales:
| Ángulo conocido | ADC | mV | Valor mapeado |
| :--- | :--- | :--- | :--- |
| 0° | 1366 | 1100 | 0 |
| 45° | 2167 | 1746 | 45 |
| 90° | 3056 | 2462 | 90 |
* ### Rango obtenido Y Decisiones de Diseño:
   | Parámetro | Valor Mínimo | Valor Máximo | Mapeo Final |
   | :--- | :---: | :---: | :---: |
   | **Voltaje (mV)** | 863 mV (`mV mínimo`) | 1338 mV (`mV máximo`) | 0° a 90° |
Decisiones de diseño: 

  1. **Montaje del Hardware fuera del Protoboard:** Se se optó por **no conectar directamente la tarjeta ESP32 a la protoboard** para la preservación de este componente. En su lugar, el circuito divisor de tensión (flex sensor + resistencia de 47 kΩ) y las conexiones hacia el ESP32 se realizaron de manera externa por medio de jumpers.

  2. **Interfaz de Usuario (MIT App Inventor) con Indicador tipo Gauge:** Para la visualización en tiempo real en la aplicación Android, se implementó un indicador gráfico tipo **Gauge (reloj/aguja)** diseñado mediante `Canvas`. Se configuró la aguja para que rote dinámicamente y se incline de forma idéntica al ángulo de flexión medido, imitando la aguja de un reloj. Esta decisión de diseño permite interpretar el grado de inclinación de manera visual e inmediata, complementando el valor numérico y la gráfica histórica de datos.

