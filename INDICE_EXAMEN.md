# Índice de Entrega de Examen Académico

## 1. Datos del Equipo e Identificación
- **Nombre:** Luis Angel Agustin
- **Boleta:** 2024630134
- **Curso:** Aplicaciones para Redes / Ingeniería en Sistemas Computacionales (IPN)
- **Repositorio Base:** [gabrielhuav/PolitecnicoOpenWorld](https://github.com/gabrielhuav/PolitecnicoOpenWorld)
- **Fork Propio:** https://github.com/luisAgt/PolitecnicoOpenWorld

---

## 2. Información del Proyecto y PR
- **Objetivo:** Implementar reproducción de audio en eventos de victoria, derrota e inicio de ronda en el minijuego.
- **Alcance:** Modificación del módulo `SoundManager.kt` en la capa de audio Android.
- **Issue / Bug asignado:** Omisión de audio en efectos de fin de ronda por desfasamiento asíncrono.
- **Pull Request:** https://github.com/gabrielhuav/PolitecnicoOpenWorld/pull/170

---

## 3. Matriz de Pruebas y Evidencias (QA)

Ruta de evidencias almacenadas en el repositorio: `PolitecnicoOpenWorld/app/src/main/assets/DOCS/`

| ID Caso | Descripción | Comportamiento Inicial (Old) | Comportamiento Corregido (New) | Estado |
| :--- | :--- | :--- | :--- | :---: |
| **CP-01** | SFX/Voz de Victoria | Silencio total al ganar la ronda | Audio y voz del personaje suenan inmediatamente | **PASSED** |
| **CP-02** | SFX de Derrota | El sonido de defeat se omitía | Sonido de derrota se ejecuta al finalizar la ronda | **PASSED** |
| **CP-03** | SFX de Derrota | El sonido de defeat se omitía | Sonido de derrota se ejecuta al finalizar la ronda | **PASSED** |

---

## 4. Revisión Técnica y Conversación entre Compañeros

- **Revisor asignado:** Jesus Angel Gonzalez Arel
- **Caso reproducido por el revisor:** CP-01 en el SHA entregado.
- **Observación recibida en GitHub:**
  > Technical review of b33b0dbf66e387db1c5ac0c282f44fada7ddcb6b (head of fix-audio). I read the full diff and built and ran this exact SHA
- **Enlace a la conversación de revisión:** https://github.com/gabrielhuav/PolitecnicoOpenWorld/pull/170#pullrequestreview-5382923375

---

## 5. Bitácora Individual y Declaración de IA

### Bitácora de Commits
- Commit de corrección: `fix(audio): resolve SoundPool async load issue for round state effects`

### Declaración de Uso de Herramientas de Inteligencia Artificial
- **Herramienta utilizada:** Gemini (Asistente de código).
- **Propósito:** Diagnóstico del flujo asíncrono entre `SoundPool.setOnLoadCompleteListener` y el ciclo de vida de Jetpack Compose (`LaunchedEffect`), identificación de las guardas en `loadedSounds` que descartaban el audio y estructuración del reporte de QA.

---

## 6. Dictamen de Calidad y Conclusiones
La corrección eliminó la latencia y la omisión de efectos auditivos durante los eventos de fin de ronda sin comprometer la estabilidad de la aplicación. Se validó la ejecución en dispositivo físico/emulador con evidencia grabada y revisión técnica en GitHub.
