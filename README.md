# Voice-Assistant-Config
Mi configuración de prueba para un voice assistant utlizando un ESP32-S3 N8R2, basado en voice-pe de HA.
## Hardware
- ESP32-S3 N8R2
- MAX98357
- INP441
- WS2812B - 3 LEDs
- AWG24 wire
- Speaker 3W
- Push button
## Conexiones
### INP441
- LRC	GPIO35   LRCLK (WS)	Word Select
- BCK	GPIO36	BCLK (SCK)	Reloj serial
- DOUT	GPIO37	DIN (SD)	Datos del micrófono
- VDD	3.3V	Alimentación	Usar regulador si > 3.3V
- GND	GND	Tierra
### MAX98357
DIN	GPIO16	DOUT (Datos I2S)	Datos al amplificador
LRC	GPIO17	LRCLK (WS)	Opcional*
BCK	GPIO18	BCLK (SCK)	Opcional*
VDD	5V	Alimentación	
GND	GND	Tierra
### WS2812B
DI	GPIO38	Datos LED	Resistencia 220Ω recomendada
VCC	5V	Alimentación	
GND	GND	Tierra
### Push button
SW	GPIO0	Botón a GND	Con resistencia pull-up interna
### Alimentación
3.3V	3.3V	Micrófono	
5V	5V	Amplificador + LEDs	Verificar corriente requerida

## Diagrama visual
ESP32-S3
├─ INMP441
│  ├─ LRC  → GPIO35
│  ├─ BCK  → GPIO36
│  └─ DOUT → GPIO37
├─ MAX98357 
│  ├─ DIN  → GPIO16
│  ├─ LRC  → GPIO17 (opcional)
│  └─ BCK  → GPIO18 (opcional)
├─ WS2812B
│  └─ DI   → GPIO38
└─ Botón
   └─ SW   → GPIO0 (a GND)
