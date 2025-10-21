# PLC Siemens

## 1. Características generales

En los laboratorios de la *Universidad Santo Tomás (USTA Bogotá)* se emplea el **PLC Siemens SIMATIC S7-1200**, un controlador lógico programable diseñado para tareas de automatización industrial a nivel educativo y profesional.

**Características principales:**
- **Fabricante:** Siemens AG  
- **Familia:** SIMATIC S7-1200  
- **Alimentación:** 120–230 V AC  
- **Entradas digitales (DI):** 14 (24 V DC)  
- **Salidas digitales (DO):** 10 (relevadores o transistores, según versión)  
- **Entradas analógicas (AI):** 2 (0–10 V)  
- **Memoria de usuario:** 100 kB aprox.  
- **Velocidad de procesamiento:** 0.1 µs por instrucción booleana  
- **Comunicación integrada:** PROFINET (Ethernet industrial)  
- **Software de programación:** TIA Portal (Totally Integrated Automation)  
- **Capacidad de expansión:** hasta 8 módulos adicionales (E/S, comunicación o tecnología)

---

## 2. Partes y componentes principales

| **Componente** | **Descripción** |
|-----------------|-----------------|
| **CPU (Unidad Central de Procesamiento)** | Es el núcleo del sistema. Contiene el microprocesador, memoria, sistema operativo y puertos de comunicación. Ejecuta cíclicamente el programa del usuario. |
| **Entradas Digitales (DI)** | Reciben señales binarias (0/1) de sensores, interruptores o pulsadores. |
| **Salidas Digitales (DO)** | Envían señales de control hacia actuadores como relés, contactores o lámparas. |
| **Entradas Analógicas (AI)** | Reciben señales proporcionales (0–10 V, 4–20 mA) desde transductores o potenciómetros. |
| **Salidas Analógicas (AO)** | (Opcionales) Generan señales proporcionales hacia variadores o actuadores analógicos. |
| **Puerto PROFINET (Ethernet)** | Permite la comunicación entre PLCs, HMIs o sistemas SCADA. |
| **Módulos de Expansión** | Permiten ampliar el número de entradas/salidas o agregar nuevos protocolos (RS-485, PROFIBUS, GPRS, etc.). |
| **Fuente de Alimentación** | Provee energía de 24 V DC al sistema y sus módulos. |
| **Bornes y Bus Interno (Backplane)** | Distribuyen alimentación y señales entre la CPU y los módulos laterales. |
| **LEDs de Estado** | Indican condiciones del sistema: RUN/STOP, ERROR, E/S activas, comunicación. |

---

## 3. Arquitectura funcional

El PLC Siemens S7-1200 cuenta con una arquitectura modular y jerárquica que incluye:

Nivel de control lógico: ejecuta el código del usuario (diagramas Ladder, FBD, STL o SCL).

Nivel de comunicación: gestiona la transferencia de datos hacia HMIs, SCADA o PLCs esclavos.

Nivel de supervisión: mediante software como TIA Portal, WinCC o TIA Web Server.

Nivel de campo: sensores y actuadores conectados directamente a las entradas/salidas.

---

## 4. Protocolos de comunicación utilizados

### 4.1. PROFINET
- **Tipo:** Ethernet Industrial (IEEE 802.3).  
- **Función:** Comunicación en tiempo real entre PLC, HMI, variadores y módulos remotos.  
- **Topología:** Estrella o línea.  
- **Velocidad:** 100 Mbps (Full-duplex).  
- **Usos en la USTA:** Integración con HMI KTP700 y variadores SINAMICS.

**Ventajas:**
- Comunicación determinística.  
- Diagnóstico integrado en TIA Portal.  
- Configuración automática de dispositivos.

---

### 4.2. MODBUS RTU / ASCII
- **Tipo:** Serie (RS-485).  
- **Función:** Comunicación maestro-esclavo con sensores o controladores externos.  
- **Velocidad:** hasta 115 kbps.  
- **Usos:** Integración de dispositivos de terceros (medidores, controladores, etc.).

**Ventajas:**
- Estructura simple y abierta.  
- Bajo costo de implementación.

---

### 4.3. MODBUS TCP/IP
- **Tipo:** Ethernet TCP/IP.  
- **Función:** Versión moderna del Modbus RTU sobre Ethernet.  
- **Usos:** Integración con sistemas SCADA como Ignition o LabVIEW.

---

### 4.4. PROFIBUS-DP
- **Tipo:** Red de campo RS-485.  
- **Función:** Comunicación entre PLC y periféricos distribuidos (ET200, variadores).  
- **Velocidad:** hasta 12 Mbps.  
- **Topología:** Línea bus.  
- **Nota:** Aunque más común en S7-300, puede añadirse al S7-1200 mediante módulo CM 1242-5.

---

### 4.5. OPC UA (Open Platform Communications Unified Architecture)
- **Tipo:** Protocolo orientado a servicios (SOA).  
- **Función:** Comunicación segura entre PLC y software de nivel superior (bases de datos, IoT, nube).  
- **Ventajas:** Cifrado, interoperabilidad, y escalabilidad.  
- **Usos:** Integración con sistemas IIoT o plataformas en la nube.


