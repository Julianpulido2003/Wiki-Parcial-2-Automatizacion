# Wiki-Parcial-2-Automatizacion
# Automatización de Máquina Dispensadora de Café


## Arquitectura del Sistema
### Componentes Utilizados
- **PLC compatible con OpenPLC** (para controlar el proceso)
- **ESP32** (para monitoreo y conectividad)
- **Bombas de agua** (para transportar el agua y el café líquido)
- **Motor con varilla mezcladora** (para la mezcla en el recipiente)
- **Sensor infrarrojo** (para detectar y contar los vasos)
- **Botón de Start y Stop** (para el control manual del proceso)
- **Indicadores LED** (para cada etapa del proceso)
- **Pantalla HMI en CODESYS** (para visualización en tiempo real del estado del sistema)

## Funcionamiento
1. Se presiona el botón de **Start** para iniciar el proceso.
2. Se activan las bombas de agua para transportar el café y el agua al recipiente de mezcla.
3. Se acciona el motor mezclador para homogeneizar la mezcla.
4. Se activa la bomba de salida para dispensar el café en el vaso.
5. Un sensor infrarrojo verifica la presencia del vaso y contabiliza los vasos servidos.
6. Los LEDs indican el estado del proceso en cada etapa.
7. La interfaz HMI muestra el estado del sistema en tiempo real.
8. Si se detecta un error o se presiona el botón de **Stop**, el proceso se detiene.

## Restricciones de Diseño
- El proceso debe completarse en un tiempo máximo de 1 minuto.
- La detección de vasos debe ser precisa y evitar falsos positivos.
- La integración con ESP32 debe permitir la recolección de datos sin afectar la automatización principal.

## Diagrama de Circuito Eléctrico
_(Agregar imagen del diagrama)_

## Definición de Variables
| Nombre | Atributo | Tipo | Descripción |
|--------|----------|------|-------------|
| Start_Button | Entrada | Digital | Botón de inicio del proceso |
| Stop_Button | Entrada | Digital | Botón de parada de emergencia |
| Water_Pump | Salida | Digital | Activa la bomba de agua |
| Coffee_Pump | Salida | Digital | Activa la bomba de café |
| Mixer_Motor | Salida | Digital | Activa el mezclador |
| Dispenser_Pump | Salida | Digital | Activa la bomba de salida |
| Cup_Sensor | Entrada | Digital | Detecta la presencia del vaso |
| LED_Stage1 | Salida | Digital | Indica la etapa de llenado |
| LED_Stage2 | Salida | Digital | Indica la etapa de mezcla |
| LED_Stage3 | Salida | Digital | Indica la etapa de dispensado |
| Cup_Counter | Contador | Entero | Cuenta la cantidad de vasos servidos |

## Diagrama de Actividades
![image](https://github.com/user-attachments/assets/b9a96d61-5f3d-4f70-941f-7eeb68ecad50)


## Programación LADDER
_(Agregar código y documentación de la programación en Ladder)_

## Implementación y Validación
- **Pruebas de Sensores:** Se verificó el funcionamiento del sensor infrarrojo para la detección del vaso.
- **Pruebas de Actuadores:** Se probaron las bombas de agua y café, así como el motor mezclador.
- **Simulación en HMI:** Se desarrolló la interfaz en CODESYS y se verificó su correcto funcionamiento.
- **Integración del ESP32:** Se validó la recepción de datos y su transmisión a una base de datos externa.

## Conclusiones
- Se logró la automatización completa del proceso de dispensado de café.
- La implementación del ESP32 permitió la recolección de datos de manera eficiente.
- Se identificaron mejoras potenciales en la integración con la pantalla LCD.
##  Roles del Equipo

| Integrante | Rol | Contribuciones |
|------------|-----|---------------|
| Julian Pulido | Diseño y construcción de la maqueta, Wiki |  
| Farouk Abdala | Diseño y construcción de la maqueta, Montaje del hardware | 
| Juan Diego Garcia | HMI, programación y simulación |  


## 📌 Restricciones y Estándares
- **Restricciones**: No se logró implementar la pantalla LCD debido a problemas de compatibilidad con librerías.
- **Estándares aplicados**: IEC 61131-3 (programación de PLCs), normas de seguridad en automatización industrial.
