# Arrancar

App web instalable (PWA) para vencer la inercia inicial: empiezas **solo 5 minutos**
y, al terminar, decides si sigues. Funciona en celular, laptop y PC desde el navegador.

## Qué hace la v0
- Botón único "Empezar 5 minutos" con el primer paso concreto.
- Temporizador que sobrevive a recargas y al segundo plano.
- Cuenta cuántas veces sales de la app durante la sesión (señal de distracción).
- Racha de días en que llegaste al minuto 5.
- Mini-checklist diaria: agua, estiramiento, entrenamiento.

## Reglas para crecer (importante)
1. Úsala **7 días seguidos** antes de añadir nada.
2. Métrica que importa: **días con al menos 1 arranque**. No el número de funciones.
3. Solo añade una función si resuelve algo que *notaste* usándola, no algo que imaginaste.

## Limitaciones conocidas
- Los datos viven en **cada dispositivo** (no hay sincronización todavía).
- Una web **no puede bloquear** Instagram/Facebook. Eso se hace con las herramientas del
  sistema (Tiempo en pantalla / Bienestar digital).
- El aviso sonoro solo suena con la app abierta; no hay notificaciones push todavía.

## Probar en local
```bash
python3 -m http.server 8000   # y abrir http://localhost:8000
```
