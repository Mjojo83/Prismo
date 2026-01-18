# 🔺 PRISMO como Asistente Virtual
> **"Más que un chatbot."**
[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![PyQt5](https://img.shields.io/badge/GUI-PyQt5-green.svg)]()
[![Hugging Face](https://img.shields.io/badge/Models-HuggingFace-yellow.svg)](https://huggingface.co/mjojo84/Prismo)

**Prismo** es un asistente virtual, inpirado en el amo de los deseos de hora de aventura porque hace lo que tu desees. 
A diferencia de los asistentes tradicionales no tienes que programar todos sus comandos gracias a su LLM (**Qwen3-VL-8B-Instruct**) no le tienes que pasar todas las instrucciones en codigo, como los asistentes normales, Prismo puede crear sus **propios comandos**. Ademas tiene un **"Cuerpo Visual"** (Avatar 2D) que reacciona en tiempo real a la voz, el texto y el estado del sistema, todo flotando discretamente en tu escritorio mediante ventanas transparentes. 

![Image](https://github.com/user-attachments/assets/e2e79158-88bb-4502-a034-b66fa2f92dbd)
---
## ✨ Lo Chido:
**Prismo puede:**
* Como su llm es visual puede ver tu pantalla y tomar deciciones, decodifica tu pantalla en pixeles y da las coordenadas y el OS le da click a ese pixel (Falta precisión ) 
* Puede abrir paginas comandos de voz en un navegador especifico.
* Tiene un sistema de busqueda dinamica Que: cuando tu mencionas "google", "youtube" lo que le digas despues de eso lo buscara textualmente en esas plataformas. 
* Tiene un sencillo configurador de animaciones , donde puedes agregar mas 
* **Todo funciona en local**

## Estructura y funcionamiento
### 1.🎭 Modelos utiliza: 
* LLM (Large Language Model): Qwen3-VL-8B-Instruct 
* TTS (Text-to-Speech): Whisper Whisper-Large-V3-Turbo-Ct2
* STS (Speech-to-Text): F5-Spanish

## 2.🏗️ Arquitectura
* Nos inspiramos en el modelo de Pypecat (https://github.com/pipecat-ai/pipecat) en su forma de tener tuberias para reproducir los procesos de prismo de forma segura sin que se congele gracias a Pypecat aunque no copiamos su codigo , vimos el canal de Ytube de su creador y vimos la arquitectura y separamos los hilos de informacion para que el del LLm que es mas importante no se congele.
* El modelo Open-LLM-VTuber nos inpiramos de su modo ventana invisible y poder traer tu avatar a donde quieras (https://github.com/Open-LLM-VTuber/Open-LLM-VTuber/tree/main) ,pero com outilizaban JAVA para implementar eso mejor decidimos mejor implementarlo en python.


### 3. 🛠️ Prismo Studio & Configurador
* **Configurador.py**: Prismo tiene un archivo llamado configurador.py , este archivo puede configurar los modelos de LLM , 
* Tiene un sencillo configurador de animaciones , donde puedes agregar más✨


## Notas:
* La pantalla la decodificamos en pixeles asi el modelo ubica mas los objetivos que sin ella (hicimos pruebas)
**Importante:** Se configuro a prismo para que trabaje con una pantalla ultrawide (32 pulgas) por lo que hizo unas modificaciones pero si tienes la normal o estandar (24 pulgadas) quita ese codigo asi funcionaria mucho mejor, de hecho el sistema esta diseñado para trabajar en 24 pero lo modificamos para que pudiera funcionar en la mia.
* Hay dos frenos de "emergencia"- al momento de probarlo y como prismo podia usar el cursor, aveces modificaba su codigo y se salia de control asi que decidimos poner un 2 breaks en el codigo, el primero es con la tecla "**Esc**" y con el comando de voz "Para".


## Importante.
* Necesitas un hardware potente, Prismo ocupa alrededor de 15GB de memoria VRAM por lo que una tarjeta grafica es necesaria, ocupe una 3090 con 24 VRAM , por lo que no tuve problemas para trabajar(Aparte de que funiona con drivers de nvidia que ya estan en la carpeta del codigo)
* Tambien probamos con otros LLM con vision como Gema de google pero como estan entrenados de otra forma la parte de los pixeles no funciono , asi que si quieren probar otro modelo , tendran que experimentar
  Solo funciona bien con la familia de Qwen3-VL
* En la rama central de las carpetas viene una que dice documentacion, ahi hay instrucciones mas detalladas

#🎭 Links de los modelos:
* Prismo de huggingface: https://huggingface.co/mjojo84/Prismo
* Para los LLM tendras que descargar ollama y copiar y pegar este comando ( ollama run qwen3-vl:8b-instruct ) en un cmd.
* Para STS vamos a utilizar el F5-Spanish que es un modelo con un fine tuning de español latino , que aun NO IMPLEMENTAMOS.
* Para TTS utilizamos whisper (https://huggingface.co/deepdml/faster-whisper-large-v3-turbo-ct2/tree/main)
 
## 🔺Prismo es un proyecto aun en desarrollo si alguno de ustedes puede mejorarlo, mejorelo. (🔺_🔺)
### Prueba 1 puede programa
https://youtu.be/5-FC9TVzTKE

### Prueba 2 valores visuales
https://youtu.be/xVUw5e8hzd8

### Prueba 3 textos personalizados
https://youtu.be/3uBN8LsBuxw
