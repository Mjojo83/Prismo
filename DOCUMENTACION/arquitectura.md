# Arquitectura de Prismo

## Concepto General
Prismo consta de dos procesos independientes que se comunican vía TCP Localhost.

1. **CEREBRO (Python)**: Maneja la inteligencia, lógica, y conexión con APIs.
2. **CUERPO (Godot)**: Maneja la representación visual, animaciones y ventana transparente.

## Protocolo de Comunicación
- **Transporte**: TCP Socket
- **Host**: 127.0.0.1
- **Puerto**: 5000 (Configurable en .env)
- **Formato**: JSON strings delimitados por `\n` (salto de línea).

### Ejemplo de Mensaje
```json
{"action": "listen"}
```
(Seguido de `\n`)

## Estructura de Directorios

### CEREBRO
- `CORE/servidor.py`: Servidor Asyncio. Mantiene conexiones y rutea mensajes.
- `main.py`: Punto de entrada.

### CUERPO
- `Scripts/Network/SocketClient.gd`: Cliente TCP. Mantiene conexión y emite señales.
- `Scripts/Managers/WindowManager.gd`: Maneja `DisplayServer` para transparencia y passthrough.
