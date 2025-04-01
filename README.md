# Wiki-Parcial-2-Automatizacion
# 📌 Proyecto: Automatización de Máquina Dispensadora de Café

## 📖 Descripción
Este proyecto consiste en la automatización de una máquina dispensadora de café para la empresa **Café & Máquinas S.A.** utilizando **PLC, sensores y actuadores**. La automatización permitirá optimizar el proceso de preparación de café, incorporando un sistema dispensador automático de vasos y un mecanismo de conteo de unidades servidas.

## ⚙️ Funcionamiento

1. Preparación
   - El café líquido y el agua están almacenados en recipientes separados.
   - Un sensor infrarrojo detecta la presencia de un vaso en la zona de dispensado.

2. Proceso de Mezcla
   - Dos **bombas de agua** transportan el café y el agua al recipiente de mezcla.
   - Un **motor con varilla mezcladora** homogeniza el contenido.
   - Una tercera **bomba** transporta el café preparado al vaso.

3. Indicadores y Control
   - Un **botón de inicio (Start)** activa el proceso.
   - Un **botón de parada (Stop)** detiene el proceso en cualquier etapa.
   - **LEDs indicadores** muestran el estado del proceso:
     - Paso del agua al mezclador
     - Paso del café al mezclador
     - Mezcla en el recipiente
     - Dispensado del café en el vaso
   - Si ocurre un error, se mostrará una alerta visual.

4. **Interfaz HMI**
   - Simulación del proceso en **CODESYS**.
   - Animaciones en tiempo real que reflejan cada etapa.
   - Indicadores de sensores y actuadores.

## 🔧 Componentes Utilizados

| Componente          | Función |
|---------------------|---------|
| PLC OpenPLC        | Control lógico del sistema |
| Sensor infrarrojo  | Detección de vaso y conteo |
| Bombas de agua (3) | Transporte de líquidos |
| Motor con varilla  | Mezcla de café y agua |
| Botones (Start/Stop) | Inicio y parada del proceso |
| LEDs indicadores   | Estado del proceso |

## 🖥️ Diagramas

### 🔌 Conexión de Sensores y Actuadores
*(Adjuntar diagrama eléctrico aquí)*

### 🔄 Diagrama de Flujo del Proceso
*(Adjuntar diagrama de actividades/secuencial aquí)*

## 📝 Código LADDER
```ladder
(* Aquí va la lógica de programación en LADDER *)
```

## 👥 Roles del Equipo

| Integrante | Rol | Contribuciones |
|------------|-----|---------------|
| Integrante 1 | Diseño y programación | Desarrollo del código LADDER, integración de sensores |
| Integrante 2 | Electrónica y conexiones | Montaje del hardware, conexión de actuadores |
| Integrante 3 | HMI y simulación | Diseño del HMI en CODESYS, pruebas y validación |

## 🚀 Resultados
- Simulación funcional en HMI.
- Implementación del prototipo físico con sensores y actuadores.
- Documentación completa del proceso.

## 📌 Restricciones y Estándares
- **Restricciones**: No se logró implementar la pantalla LCD debido a problemas de compatibilidad con librerías.
- **Estándares aplicados**: IEC 61131-3 (programación de PLCs), normas de seguridad en automatización industrial.
