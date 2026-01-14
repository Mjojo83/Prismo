# 📘 MANUAL DE OPERACIONES - PRISMO AI

Este documento detalla las funciones críticas, mecanismos de seguridad y la estructura correcta para operar a Prismo de manera segura y eficiente.

---

## 🚨 1. FRENOS DE MANO (SEGURIDAD)
Prismo cuenta con dos mecanismos de emergencia para detener acciones no deseadas o bucles infinitos.

### A. 🛑 EL BOTÓN ROJO (Tecla `ESC`)
*   **Función**: Detiene TOTALMENTE el programa y mata el proceso.
*   **Cuándo usarlo**: Si Prismo entra en un bucle visual infinito, empieza a hacer clics erráticos o necesitas apagarlo inmediatamente.
*   **Acción**: Presiona la tecla `ESC` en tu teclado. Verás un mensaje en consola indicando "Safe Mode Activated" y el sistema se cerrará.

### B. ✋ COMANDO DE VOZ "ABORTA"
*   **Función**: Cancela la misión actual pero mantiene a Prismo encendido.
*   **Cuándo usarlo**: Si Prismo entendió mal tu orden, está navegando a una página equivocada o simplemente cambiaste de opinión.
*   **Acción**: Di claramente **"Prismo, aborta"** o **"Aborta misión"**.
*   **Resultado**: Prismo dejará de hacer lo que estaba haciendo, limpiará su memoria de la tarea actual y volverá a esperar instrucciones ("Estado IDLE").

---

## 🗣️ 2. ESTRUCTURA DE COMANDOS HÍBRIDOS (LA REGLA DE ORO)
Para que Prismo funcione con máxima precisión al navegar por internet, debes usar la **Estructura Segmentada**. Esta estructura permite al sistema saber exactamente qué buscar y qué hacer después.

### La Fórmula Mágica:
> `[Plataforma]` + `[Búsqueda]` + **" y "** + `[Acción Visual]`

### 🟢 Ejemplos Correctos:
1.  *"Ponle en **YouTube** Juan Gabriel **y** luego dale clic a la primera canción que veas."*
2.  *"Busca en **Amazon** zapatillas Nike **y** selecciona las que sean rojas."*
3.  *"Abre **Spotify** y pon música relajante **y** dale al botón de play."*

### 🔴 Por qué fallan otros comandos:
*   *"Busca Juan Gabriel en YouTube"* (Sin el "y"): Prismo buscará, pero no sabrá qué hacer después, quedándose esperando o adivinando.
*   *"Quiero ver videos de gatos"* (Sin plataforma explícita): Prismo intentará usar visión pura en lugar de navegación rápida, lo cual es más lento.

**NOTA IMPORTANTE**: La palabra **" y "** (con espacios) es el separador clave. Prismo usa este conector para dividir su cerebro en dos: una parte navega (URL) y la otra mira (Visión Artificial).

---

## ⚙️ 3. CONFIGURACIÓN TÉCNICA Y ARCHIVOS CLAVE

### 🧠 ¿Dónde vive el System Prompt?
*   **Archivo**: `PROYECTO_PRISMO\CEREBRO\HABILIDADES\cerebro_llm.py`
*   **Variable**: `system_prompt` (dentro de la clase `CerebroLLM`).
*   **Qué hace**: Define la personalidad de Prismo, sus reglas de comportamiento JSON y cómo debe responder a los estímulos visuales. Aquí se le enseña a devolver coordenadas `[ACCION: CLIC...]`.

### 🌐 ¿Dónde se configuran los Atajos Web (Triggers)?
*   **Archivo**: `PROYECTO_PRISMO\CEREBRO\config_web.json` (Generado dinámicamente o editable manualmente).
*   **Estructura**:
    ```json
    {
      "youtube": {
        "url_plantilla": "https://www.youtube.com/results?search_query={}",
        "ruta_navegador": "C:/Program Files/Google/Chrome/Application/chrome.exe"
      }
    }
    ```
*   **Cómo funciona**: Cuando dices "YouTube", Prismo busca en este archivo. Si encuentra la clave, usa la `url_plantilla` e inserta tu búsqueda donde está el `{}`.

### 🚀 ¿Dónde se configuran las Apps Locales?
*   **Archivo**: `PROYECTO_PRISMO\CEREBRO\config_apps.json`
*   **Uso**: Para abrir programas como Word, Excel, Calculator, etc., sin necesidad de buscar en internet.

---

## 🛡️ 4. CONSIDERACIONES Y MANTENIMIENTO

1.  **Limpieza de Logs**: Prismo genera logs en consola. Si ves errores de `UnicodeEncodeError`, es probable que la consola de Windows no soporte emojis. Los logs críticos ahora usan texto plano (`[OK]`, `[ERROR]`).
2.  **Iluminación Visual**: Prismo "ve" lo que hay en tu monitor principal. Asegúrate de que las ventanas emergentes o notificaciones no tapen el objetivo, ya que esto puede confundir a la visión artificial.
3.  **Filtro de Seguridad**: En `manos.py` existe un "Hard Filter" que impide que Prismo escriba palabras del sistema (como "auto_check" o "misión actual") en tus documentos. Si ves un aviso `🛑 BLOQUEO DE SEGURIDAD`, es este filtro protegiéndote.

---
*Documento actualizado automáticamente por Antigravity - Diciembre 2025*
