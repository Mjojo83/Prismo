# 🔺 PRISMO AI: Tu Asistente de Escritorio Reactivo (2D Visual)

> **"Más que un chatbot, un compañero que vive en tu pantalla."**

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![PyQt5](https://img.shields.io/badge/GUI-PyQt5-green.svg)]()
[![Hugging Face](https://img.shields.io/badge/Models-HuggingFace-yellow.svg)](AQUI_TU_LINK_DE_HUGGING_FACE)

**Prismo** es un asistente virtual modular diseñado para romper la barrera entre la consola de comandos y la interacción visual. A diferencia de los asistentes tradicionales, Prismo posee un **"Cuerpo Visual"** (Avatar 2D) que reacciona en tiempo real a la voz, el texto y el estado del sistema, todo flotando discretamente en tu escritorio mediante ventanas transparentes.

---

## ✨ Lo Chido: Características Principales

### 1. 🎭 Arquitectura de "Cuerpo y Cerebro"
Prismo separa la lógica de pensamiento de su representación visual, permitiendo un rendimiento fluido sin congelamientos.
* **Modo Reposo (El Cubo):** Un widget minimalista en forma de cubo que espera tus órdenes en la esquina de la pantalla.
* **Transformación Cinemática:** Al invocarlo (doble clic), el cubo explota/gira y se transforma en el Avatar completo.
* **Reactividad:** El avatar cambia de estado (Idle, Pensando, Hablando) basándose en lo que ocurre en la consola.

### 2. 🗣️ Sincronización Labial (Lip-Sync) Híbrida
No es un GIF estático. Prismo escucha el flujo de salida de la consola (TTS o Texto):
* Cuando la IA responde, Prismo **mueve la boca automáticamente**.
* Al terminar la respuesta, regresa instantáneamente a su estado de reposo (parpadeo sutil).
* Soporte para animaciones fluidas basadas en secuencias de PNG (no GIFs pesados) para mayor control de FPS.

### 3. 🛠️ Prismo Studio & Configurador
Incl
