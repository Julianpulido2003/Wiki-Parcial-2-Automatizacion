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
- **4 Relays** ( para lka alimentación correcta de todos los componentes)
### 1. Diseño
Se estableció la lógica del funcionamiento del sistema:
- El agua y el café líquido se almacenan en recipientes separados.
- Dos bombas de agua transportan los líquidos a un recipiente de mezcla.
- Un motor con una varilla mezcladora realiza la homogeneización del café.
- Una tercera bomba dispensa la mezcla en el vaso.
- Un sensor infrarrojo detecta la presencia del vaso y cuenta la cantidad de unidades servidas.
- Se utilizan LEDs para indicar cada etapa del proceso.
- Botones físicos de **Start** y **Stop** controlan la ejecución del sistema.
- Se implementó una simulación en HMI para visualizar el proceso.

### 2. Desarrollo
Se utilizó **CODESYS** para la programación del PLC en lenguaje **LADDER** y se integró un **ESP32** para la gestión de sensores y comunicación con el sistema.

### 3. Implementación
- Se utilizaron **cuatro relays** para la alimentación de los componentes eléctricos.
- Sensores infrarrojos para la detección de vasos.
- Bombas de agua y un motor mezclador para la preparación del café.
- LEDs indicadores para cada fase del proceso.
- Simulación en HMI mostrando el estado del sistema en tiempo real.

### 4. Validación
El sistema fue probado en diferentes escenarios para garantizar su correcto funcionamiento. Se verificó el flujo de líquidos, la detección de vasos y la correcta activación de cada componente en su etapa correspondiente.

## Restricciones de Diseño
- El proceso debe completarse en un tiempo máximo de 1 minuto.
- La detección de vasos debe ser precisa y evitar falsos positivos.
- La integración con ESP32 debe permitir la recolección de datos sin afectar la automatización principal.

## Diagrama HMI
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

## Fabricación de la Maqueta

### Bocetación
La maqueta se diseñó dividiendo un cubo en tres zonas principales:
1. **Zona de recipientes y bombas:** Contiene los depósitos de agua, café y mezclador junto con las bombas que transportan los líquidos.
2. **Zona de circuitos:** Aislada para evitar contacto con líquidos y proteger los componentes eléctricos.
3. **Zona de dispensación de café:** Donde el café se vierte en el vaso después de ser mezclado.

### Materiales
- Cartón craft y cartón piedra para la base.
- Huecos perforados para la instalación de LEDs e integración de mangueras de dispensación.
- Mecanismo de mezclado con motor y varilla mezcladora.
- Cuatro relés para la alimentación de los componentes.
- Cableado estructurado para la conexión de todos los elementos eléctricos.
## Maqueta 
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

| Integrante | Rol |
|------------|-----|
| Julian Pulido | Diseño y construcción de la maqueta, Wiki |  
| Farouk Abdala | Diseño y construcción de la maqueta, Montaje del hardware | 
| Juan Diego Garcia | HMI, programación y simulación |  


## 📌 Restricciones y Estándares
- **Restricciones**: No se logró implementar la pantalla LCD debido a problemas de compatibilidad con librerías.
- **Estándares aplicados**: IEC 61131-3 (programación de PLCs), normas de seguridad en automatización industrial.
