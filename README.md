# Controlador para Motor BLDC - Shell Eco-Marathon

## Descripción General del Controlador

Este repositorio documenta el desarrollo de un controlador para motores BLDC, diseñado específicamente para el vehículo de la competencia Shell Eco-Marathon. Utilizando un microcontrolador STM32F103C8T6, el controlador permite un control preciso y eficiente, aprovechando técnicas avanzadas de modulación y control para maximizar el rendimiento energético en entornos de competición.

### Arquitectura y Componentes Clave

1. **Microcontrolador**: Se utiliza el STM32F103C8T6, programado en C/C++ desde el entorno STM32CubeIDE. Este controlador procesa las señales de control y coordina la secuencia de fases del motor mediante señales PWM.
  
2. **Control de Fase mediante Sensores Hall**: Para detectar la posición del rotor, se emplean sensores de efecto Hall, los cuales determinan la secuencia de conmutación para ajustar la rotación del motor en todas las velocidades.
  
3. **Gate Driver y MOSFETs de Potencia**: Se utilizan MOSFETs de baja resistencia Rds(on) y un controlador de puerta adecuado para un cambio rápido y eficiente, basándose en ejemplos que utilizan drivers como el 2ED2184.
  
4. **Sensor de Corriente**: La corriente en cada fase se monitorea mediante sensores de efecto Hall, con la fase A configurada con un sensor ACS758 para realizar ajustes de consumo y proteger el sistema de sobrecargas.

### Características del Software

- **Modulación PWM y Secuencia Sinusoidal**: El controlador emplea una modulación de onda sinusoidal para mejorar la eficiencia, utilizando PWM configurado en el STM32 para cada fase del motor.
- **Cambio de Fase Automatizado**: Se implementa un sistema de interrupciones para cambiar de fase según la posición detectada por los sensores Hall.
- **Monitoreo de Corriente y Voltaje**: Mediante el ADC del STM32, el controlador registra y ajusta en tiempo real el consumo de energía del motor.

### Esquema de Funcionamiento

1. **Inicio Suave del Motor**: El controlador inicia en un modo de bajo consumo para reducir picos de corriente en el arranque.
2. **Detección y Control de Fase**: Los sensores Hall detectan la posición del rotor, permitiendo al controlador sincronizar la conmutación de fases.
3. **Protección y Diagnóstico**: El controlador detecta y responde ante fallos en sensores o sobrecorriente, protegiendo el sistema durante la operación.

### Documentación Técnica

Este repositorio incluye:
- **Código de Ejemplo en C/C++ para STM32**: Ejemplos de configuración del PWM y el ADC en el STM32 para el control del motor.
- **Esquemáticos y Layout de PCB**: Diagramas de conexión en plataformas como KiCad y Proteus.
- **Guías de Cálculo de Componentes**: Documentación sobre la selección y el cálculo de valores óptimos para MOSFETs y resistencias de puerta.

Para más información, consulta los documentos en este repositorio o comunícate con el equipo de desarrollo.
