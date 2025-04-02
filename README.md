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
- **4 Relays** ( para la alimentación correcta de todos los componentes)
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
Se utilizó **OPENPLC** para la programación del PLC en lenguaje **LADDER**y se integró un **ESP32** para la gestión de sensores y comunicación con el sistema. Además, se realizó la simulación HMI en **CODESYS** mostrando el estado del sistema en tiempo real.

### 3. Implementación
- Se utilizaron **cuatro relays** para la alimentación de los componentes eléctricos.
- Sensor infrarrojo para la detección de vasos.
- Bombas de agua y un motor mezclador para la preparación del café.
- LEDs indicadores para cada fase del proceso.


### 4. Validación
El sistema fue probado en diferentes escenarios para garantizar su correcto funcionamiento. Se verificó el flujo de líquidos, la detección de vasos y la correcta activación de cada componente en su etapa correspondiente.

## Restricciones de Diseño
- El proceso debe completarse en un tiempo máximo de 1 minuto.
- La detección de vasos debe ser precisa y evitar falsos positivos.
- La integración con ESP32 debe permitir la recolección de datos sin afectar la automatización principal.
## Diagrama de circuito
![image](https://github.com/user-attachments/assets/e69e8dec-2540-408f-8359-d42cae8092c0)


## Diagrama HMI
## Etapa 1
![image](https://github.com/user-attachments/assets/9f8a7a83-97b8-4167-b2f5-d24192d10634)
## Etapa 2
![image](https://github.com/user-attachments/assets/1dc7ef14-67d7-4824-b015-3daa612ea9cd)
## Etapa 3
![image](https://github.com/user-attachments/assets/0b506c51-ed29-4724-bc7d-8ebeb67311e5)





## Definición de Variables

| #  | Nombre           | Atributo         | Tipo  | Dirección | Estado Inicial | Descripción |
|----|----------------|----------------|------|------------|----------------|-------------|
| 1  | START          | Entrada        | BOOL | %IX0.0     | False          | Botón de inicio del proceso. |
| 2  | STOP           | Entrada        | BOOL | %IX0.1     | False          | Botón de parada de emergencia. |
| 3  | IR_CUP         | Entrada        | BOOL | %IX0.2     | True           | Sensor infrarrojo que detecta la presencia del vaso. |
| 4  | PumpA          | Salida         | BOOL | %QX0.0     | True           | Bomba que transporta el agua al recipiente de mezcla. |
| 5  | PumpB          | Salida         | BOOL | %QX0.1     | True           | Bomba que transporta el café al recipiente de mezcla. |
| 6  | Mixer          | Salida         | BOOL | %QX0.2     | True           | Motor que acciona la varilla mezcladora. |
| 7  | PumpCoffee     | Salida         | BOOL | %QX0.3     | True           | Bomba que transporta el café ya mezclado al vaso. |
| 8  | Lamp_Complete  | Salida         | BOOL | %QX0.4     | False          | LED indicador de que el café está listo. |
| 9  | DelayCupPlaced | Relay Interno  | TON  | -          | -              | Temporizador que retrasa el inicio si no hay un vaso. |
| 10 | TimerPumpA     | Tiempo         | TON  | -          | -              | Temporizador para controlar el tiempo de activación de la bomba de agua. |
| 11 | TimerPumpB     | Tiempo         | TON  | -          | -              | Temporizador para la bomba de café. |
| 12 | TimerMixer     | Tiempo         | TON  | -          | -              | Temporizador que regula el tiempo de mezclado. |
| 13 | TimerPumpCoffee| Tiempo         | TON  | -          | -              | Temporizador que controla el tiempo de dispensación del café al vaso. |
| 14 | CTUCups        | Contador       | CTU  | -          | -              | Contador que lleva el registro de los vasos servidos. |
| 15 | current_count  | Contador       | INT  | -          | -              | Variable que almacena la cantidad de vasos servidos. |

## Diagrama de Actividades
![image](https://github.com/user-attachments/assets/b9a96d61-5f3d-4f70-941f-7eeb68ecad50)

## Programación LADDER
![image](https://github.com/user-attachments/assets/79c43f2c-a474-43b0-aaab-e6e0a70d649a)

![image](https://github.com/user-attachments/assets/c35c8ee9-f0db-4fe0-874c-960e26fa9604)

![image](https://github.com/user-attachments/assets/8b11bd5b-dc21-4b9c-825b-b0e7585a64d4)

## Fabricación de la Maqueta

### Bocetación
La maqueta se diseñó dividiendo un cubo en tres zonas principales:
1. **Zona de recipientes y bombas:** Contiene los depósitos de agua, café y mezclador junto con las bombas que transportan los líquidos.
2. **Zona de circuitos:** Aislada para evitar contacto con líquidos y proteger los componentes eléctricos.
3. **Zona de dispensación de café:** Donde el café se vierte en el vaso después de ser mezclado.

## Maqueta 

![image](https://github.com/user-attachments/assets/e6801f5d-95b1-421b-b944-fa0ad94dd805)
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
| Julián Pulido | Diseño y construcción de la maqueta, Wiki |  
| Carlos Farouk Abdala | Diseño y construcción de la maqueta, Montaje del hardware | 
| Juan Diego Garcia | HMI, programación y simulación |  


##  Oportunidad de Mejora y Estándares
- **Oportunidad de Mejora**: No se logró implementar la pantalla LCD debido a problemas de compatibilidad con librerías.
- **Estándares aplicados**: IEC 61131-3 (programación de PLCs), normas de seguridad en automatización industrial.
