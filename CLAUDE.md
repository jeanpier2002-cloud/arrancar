# Arrancar — notas para Claude (leer al inicio de cada sesión)

Repo público: no escribir aquí datos personales, de salud ni credenciales. Solo decisiones del producto.

## Contexto
- PWA en un solo `index.html` (+ `sw.js`, `manifest.webmanifest`, íconos). Sin build, sin dependencias.
- Publicada con GitHub Pages desde `main` (/ root): https://jeanpier2002-cloud.github.io/arrancar/
- Datos en `localStorage` (clave `arrancar.v1`), **por dispositivo**. Hay copia de seguridad (exportar/restaurar JSON). No hay sincronización.
- El usuario no es programador: responder en español, claro y sin jerga. Para decisiones de producto, ser mentor honesto y cuestionar (no complacer). Para tareas de programación, ejecutar.
- Probar siempre con Playwright (móvil simulado, `page.clock`) antes de subir. Servidor local: `python3 -m http.server 8765`.

## Reglas de crecimiento (acordadas)
1. No añadir funciones por imaginación; solo por algo observado al usar la app.
2. Métrica que importa: días en que el usuario **arrancó** algo, no cantidad de funciones.
3. Una función nueva a la vez.

## HALLAZGO PENDIENTE (2026-11-09) — el temporizador de foco NO se usa
- El usuario **sí usa** el checklist (agua, estiramiento) pero **no registra el tiempo de foco** y dice que no lo hará: simplemente hace sus trabajos sin abrir el temporizador.
- Consecuencia: "minutos de foco", "arranques" y la **racha** (hoy basada solo en `reached5`) no reflejan la realidad y se quedarán en 0.
- Lección: lo que se registra es lo que se puede hacer con 1 toque, *después* de hacerlo. El temporizador exige comprometerse *antes* de empezar (más fricción).

### Qué hacer cuando el usuario retome el tema (proponer, no imponer)
1. **Preguntarle primero (honesto):** ¿arranca sin el temporizador porque ya le sale solo, o porque lo evita? Si ya arranca solo, el temporizador cumplió su objetivo y no hay que forzarlo.
2. **Reemplazo recomendado: registro de 1 toque, retroactivo**, igual que agua/estiramiento:
   - Fila "Arranqué hoy" (toggle) → es la regla de los 5 minutos como autorreporte.
   - Fila "Bloques de estudio hoy": selector 0 / 1 / 2 / 3+ (bloques de ~25 min).
3. **Racha:** que cuente un día si hay "Arranqué hoy" marcado **o** una sesión con temporizador completada (no solo `reached5`).
4. **Temporizador:** dejarlo, pero secundario (botón pequeño "Usar temporizador"); el protagonismo pasa al checklist.
5. Gráfico semanal: cambiar "minutos de foco" por bloques o días con arranque.
6. Mantener compatibilidad con datos existentes en `arrancar.v1` (no romper la copia de seguridad; si se cambia el esquema, subir a `v: 2` con migración).

## Backlog (en orden, sin prisa)
1. (arriba) Reemplazar el registro de foco.
2. Sincronización PC/celular (Supabase o Firebase, con login). Solo si el usuario la pide tras usar la app en un solo dispositivo.
3. Gastos y ahorro (solo si lo pide y tras varias semanas de uso real de lo anterior).
