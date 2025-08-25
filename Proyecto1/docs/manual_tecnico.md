# Manual Técnico - Proyecto 1

## Tabla de Contenidos
- [Manual Técnico - Proyecto 1](#manual-técnico---proyecto-1)
  - [Tabla de Contenidos](#tabla-de-contenidos)
  - [1. Objetivos](#1-objetivos)
    - [1.1 Objetivo General](#11-objetivo-general)
    - [1.2 Objetivos Específicos](#12-objetivos-específicos)
  - [2. Alcance del Proyecto](#2-alcance-del-proyecto)
    - [2.1 Inclusiones](#21-inclusiones)
    - [2.2 Exclusiones](#22-exclusiones)
  - [3. Topología de Red](#3-topología-de-red)
    - [3.1 Area Central](#31-area-central)
    - [3.2 Redacción Digital](#32-redacción-digital)
    - [3.3 Análilis de Datos](#33-análilis-de-datos)
    - [3.4 Infraestructura IT](#34-infraestructura-it)
    - [3.5 Gerencia](#35-gerencia)
  - [](#)
  - [4. Tabla de Direccionamiento IP](#4-tabla-de-direccionamiento-ip)
  - [5. Configuraciones de Dispositivos](#5-configuraciones-de-dispositivos)
    - [5.1 Área Central](#51-área-central)
      - [5.1.1 Servidor](#511-servidor)
        - [5.1.1.1 Conecciones del Servidor con sus switches adyacentes](#5111-conecciones-del-servidor-con-sus-switches-adyacentes)
      - [5.1.2 Switches en modo cliente](#512-switches-en-modo-cliente)
        - [5.1.2.1 MSW1](#5121-msw1)
        - [5.1.2.2 MSW2](#5122-msw2)
        - [5.1.2.3 MSW3](#5123-msw3)
        - [5.1.2.4 MSW4](#5124-msw4)
        - [5.1.2.5 MSW5](#5125-msw5)
        - [5.1.2.6 MSW6](#5126-msw6)
        - [5.1.2.7 Conexiones entre los Switches Cliente](#5127-conexiones-entre-los-switches-cliente)
    - [5.2 Gerencia](#52-gerencia)
      - [5.2.1 Switch MSW10](#521-switch-msw10)
      - [5.2.2 Switch SW15](#522-switch-sw15)
      - [5.2.3 Switch SW14](#523-switch-sw14)
      - [5.2.4 Switch SW13](#524-switch-sw13)
      - [5.2.5 Switch SW16](#525-switch-sw16)
      - [5.2.6 Switch SW17](#526-switch-sw17)
      - [5.2.7 Conexión entre los Switches](#527-conexión-entre-los-switches)
    - [5.3 Infraestructura IT](#53-infraestructura-it)
    - [5.4 Análissis de Datos](#54-análissis-de-datos)
    - [5.5 Redacción Digital](#55-redacción-digital)
      - [5.5.1 Switch MSW9](#551-switch-msw9)
      - [5.5.2 Switch SW18](#552-switch-sw18)
      - [5.5.2 Switch SW19](#552-switch-sw19)
      - [5.5.2 Switch SW20](#552-switch-sw20)
      - [5.5.4 Conexiones entre los Switches](#554-conexiones-entre-los-switches)



## 1. Objetivos

### 1.1 Objetivo General
 Diseñar e implementar una red LAN escalable y redundante para la empresa FIUComm Technologies, utilizando Cisco Packet Tracer. El diseño busca garantizar una comunicación interna eficiente y segura mediante la segmentación con VLANs, la administración centralizada con VTP, la prevención de bucles con STP y la optimización de enlaces con EtherChannel.

### 1.2 Objetivos Específicos
* Segmentar la red lógicamente en VLANs por departamento para mejorar la organización y seguridad.
* Implementar VTP para la administración centralizada y propagación de VLANs.
* Configurar STP para garantizar una topología de red redundante y libre de bucles.
* Utilizar EtherChannel (LACP y PAGP) para incrementar el ancho de banda y la tolerancia a fallos en enlaces troncales.
* Validar la conectividad de la red y el correcto funcionamiento de los protocolos implementados.

---

## 2. Alcance del Proyecto

### 2.1 Inclusiones
* El diseño, configuración y validación se realizan íntegramente en el simulador **Cisco Packet Tracer**.
* La topología abarca **cinco áreas funcionales**: Gerencia, Infraestructura IT, Análisis de Datos, Redacción Digital y un Backbone central.
* Configuración de VLANs, VTP (modos servidor, cliente y transparente), STP (PVST o Rapid PVST)  y EtherChannel (LACP y PAGP) siguiendo las especificaciones del proyecto.
* Asignación de direccionamiento IP  y configuración de dispositivos mediante **CLI**
* Personalización de switches seleccionados con un **banner MOTD**.

### 2.2 Exclusiones
* Configuración de enrutadores o enrutamiento inter-VLAN. El proyecto se centra en tecnologías de Capa 2.
* Conexión con redes externas (WAN/Internet).
* Implementación de mecanismos de seguridad avanzados más allá de la segmentación por VLANs.
* Implementación física del hardware de red.

---

## 3. Topología de Red

A continuación, se presenta el diagrama de la topología de red implementada en Cisco Packet Tracer para FIUComm Technologies. La red está segmentada en cinco áreas departamentales (Gerencia, Infraestructura IT, Análisis de Datos, Redacción Digital y Seguridad) que se interconectan a través de un área de Backbone central, garantizando redundancia y un flujo de tráfico organizado.
![alt text](imgs/t5.png)
### 3.1 Area Central
![alt text](imgs/t2.png)

### 3.2 Redacción Digital
![alt text](imgs/t1.png)

### 3.3 Análilis de Datos
![alt text](imgs/t0.png)

### 3.4 Infraestructura IT
![alt text](imgs/t4.png)

### 3.5 Gerencia
![alt text](imgs/t3.png)
---

## 4. Tabla de Direccionamiento IP

La siguiente tabla detalla el esquema de direccionamiento IP estático asignado a los dispositivos finales dentro de cada VLAN departamental.

| Dispositivo | Departamento (VLAN) | Dirección IP | Máscara de Subred |
| :--- | :--- | :--- | :--- |
| `PC-Gerencia-01` | `Gerencia (VLAN XX)` | `XXX.XXX.XX.XX` | `255.255.255.0` |
| `PC-Gerencia-02` | `Gerencia (VLAN XX)` | `XXX.XXX.XX.XX` | `255.255.255.0` |
| `PC-IT-01` | `Infra IT (VLAN XX)` | `XXX.XXX.XX.XX` | `255.255.255.0` |
| `PC-IT-02` | `Infra IT (VLAN XX)` | `XXX.XXX.XX.XX` | `255.255.255.0` |
| `PC-Datos-01` | `Análisis (VLAN XX)`| `XXX.XXX.XX.XX` | `255.255.255.0` |
| `PC-Datos-02` | `Análisis (VLAN XX)`| `XXX.XXX.XX.XX` | `255.255.255.0` |
| `PC-Redaccion-01`|`Redacción (VLAN XX)`| `XXX.XXX.XX.XX` | `255.255.255.0` |
| `PC-Redaccion-02`|`Redacción (VLAN XX)`| `XXX.XXX.XX.XX` | `255.255.255.0` |
| `PC-Seguridad-01`|`Seguridad (VLAN XX)`| `XXX.XXX.XX.XX` | `255.255.255.0` |
| `PC-Seguridad-02`|`Seguridad (VLAN XX)`| `XXX.XXX.XX.XX` | `255.255.255.0` |

*Nota: Reemplaza las 'XX' con los valores correspondientes de tu proyecto.*

---

## 5. Configuraciones de Dispositivos

En esta sección se documentan los comandos clave utilizados para la configuración de los switches de la red.

### 5.1 Área Central

#### 5.1.1 Servidor
Este switch actúa como VTP Server y Root Bridge para el protocolo STP.

```bash
enable
configure terminal

! Primero nombro y asigno contraseña
hostname SERVIDOR

! Configuro las vlan
vlan 10
 name Redaccion_Digital
 exit
vlan 20
 name Analisis_de_Datos
 exit
vlan 30
 name Infraestructura_IT
 exit
vlan 40
 name Seguridad
 exit
vlan 50
 name Gerencia
 exit

! Configuro el switch como servidor vtp
vtp mode server
vtp domain C2_FIUComm
vtp password proyecto12025

! Configuro STP
spanning-tree mode pvst
spanning-tree vlan 10,20,30,40,50 root primary

! -- Configuro el EtherChannel --
! Grupo 1 con pagp
interface range FastEthernet0/1 - 3
 shutdown
 channel-protocol pagp
 channel-group 1 mode desirable
 no shutdown
 exit
interface Port-channel1
 switchport mode trunk
 exit

! Grupo 2 con pagp
interface range FastEthernet0/4 - 6
 shutdown
 channel-protocol pagp
 channel-group 2 mode desirable
 no shutdown
 exit
interface Port-channel2
 switchport mode trunk
 exit


! Grupo 3 con lacp
interface range FastEthernet0/13 - 15
 shutdown
 channel-protocol lacp
 channel-group 3 mode active
 no shutdown
 exit
interface Port-channel3
 switchport mode trunk
 exit


! Grupo 4 con lacp
interface range FastEthernet0/16 - 18
 shutdown
 channel-protocol lacp
 channel-group 4 mode active
 no shutdown
 exit
interface Port-channel4
 switchport mode trunk
 exit

! Grupo 5 con lacp
interface range FastEthernet0/19 - 21
 shutdown
 channel-protocol lacp
 channel-group 5 mode active
 no shutdown
 exit
interface Port-channel5
 switchport mode trunk
 exit


 ! Grupo 6 con lacp
interface range FastEthernet0/22 - 24
 shutdown
 channel-protocol lacp
 channel-group 6 mode active
 no shutdown
 exit
interface Port-channel6
 switchport mode trunk
 exit

!Finalizo y guardo
end
copy running-config startup-config

```

##### 5.1.1.1 Conecciones del Servidor con sus switches adyacentes

   Puerto en SERVIDOR | Grupo de Canal | Protocolo | Conexión a Switch |
 |--------------------|----------------|-----------|-------------------|
 | FastEthernet 1-3   | Port-channel1  | PAgP      | MSW3, puertos 1-3 |
 | FastEthernet 4-6   | Port-channel2  | PAgP      | MSW4, puertos 4-6 |
 | FastEthernet 13-15 | Port-channel3  | LACP      | MSW2, puertos 13-15 |
 | FastEthernet 16-18 | Port-channel4  | LACP      | MSW1, puertos 16-18 |
 | FastEthernet 19-21 | Port-channel5  | LACP      | MSW6, puertos 19-21 |
 | FastEthernet 22-24 | Port-channel6  | LACP      | MSW5, puertos 22-24 |

#### 5.1.2 Switches en modo cliente

A continuación se listan las configuraciones de los switches en modo cliente junto con sus conexiones físicas tanto con el servidor como con sus clientes adyacentes.

##### 5.1.2.1 MSW1
- **Conexión:** Puertos 16-18 a SERVIDOR (LACP)
-  **Conexión 2:** Puertos 22-24 a MSW6 (LACP)

```bash
enable
configure terminal
hostname MSW1

! Configuro el cliente
vtp mode client
vtp domain C2_FIUComm
vtp password proyecto12025

! Lo configuro en LACP
interface range FastEthernet0/16 - 18
 shutdown
 channel-protocol lacp
 channel-group 4 mode active
 no shutdown
 exit
interface Port-channel4
 switchport mode trunk
 exit

! EtherChannel hacia MSW6 LACP
interface range FastEthernet0/22 - 24
 shutdown
 channel-protocol lacp
 channel-group 10 mode active
 no shutdown
 exit
interface Port-channel10
 switchport mode trunk
 exit

! Enlace Troncal hacia MSW10 (Gerencia)
interface FastEthernet0/21
 switchport mode trunk
 exit

! Termino y guardo 
end
copy running-config startup-config
```

##### 5.1.2.2 MSW2
- **Conexión 1:** Puertos 13-15 a SERVIDOR (LACP)
- **Conexión 2:** Puertos 10-12 a MSW5 (LACP)

```bash
enable
configure terminal
hostname MSW2

! Configuro el cliente
vtp mode client
vtp domain C2_FIUComm
vtp password proyecto12025

! Lo configuro en LACP
interface range FastEthernet0/13 - 15
 shutdown
 channel-protocol lacp
 channel-group 3 mode active
 no shutdown
 exit
interface Port-channel3
 switchport mode trunk
 exit

! EtherChannel hacia MSW5 (LACP)
interface range FastEthernet0/10 - 12
 shutdown
 channel-protocol lacp
 channel-group 11 mode active
 no shutdown
 exit
interface Port-channel11
 switchport mode trunk
 exit

! NUEVO Enlace Troncal hacia MSW10 (Gerencia) 
interface FastEthernet0/20
 switchport mode trunk
 exit

! Termino y guardo
end
copy running-config startup-config
```

##### 5.1.2.3 MSW3
- **Conexión 1:** Puertos 1-3 a SERVIDOR (PAgP)
- **Conexión 2:** Puertos 4-6 a MSW6 (PAgP)

```bash
enable
configure terminal
hostname MSW3

! Configuro el cliente
vtp mode client
vtp domain C2_FIUComm
vtp password proyecto12025

! Lo configuro en LACP
interface range FastEthernet0/1 - 3
 shutdown
 channel-protocol pagp
 channel-group 1 mode desirable
 no shutdown
 exit
interface Port-channel1
 switchport mode trunk
 exit

! EtherChannel hacia MSW6 (PAgP)
interface range FastEthernet0/4 - 6
 shutdown
 channel-protocol pagp
 channel-group 12 mode desirable
 no shutdown
 exit
interface Port-channel12
 switchport mode trunk
 exit

! Enlace Troncal hacia MSW9 (Redacción Digital)
interface FastEthernet0/24
 switchport mode trunk
 exit

! Termino y guardo 
end
copy running-config startup-config
```

##### 5.1.2.4 MSW4
- **Conexión 1:** Puertos 4-6 a SERVIDOR (PAgP)
- **Conexión 2:** Puertos 7-9 a MSW5 (PAgP)

```bash
enable
configure terminal
hostname MSW4

! Configuro el cliente
vtp mode client
vtp domain C2_FIUComm
vtp password proyecto12025

! Lo configuro en LACP
interface range FastEthernet0/4 - 6
 shutdown
 channel-protocol pagp
 channel-group 2 mode desirable
 no shutdown
 exit
interface Port-channel2
 switchport mode trunk
 exit

 !  EtherChannel hacia MSW5 (PAgP)
interface range FastEthernet0/7 - 9
 shutdown
 channel-protocol pagp
 channel-group 13 mode desirable
 no shutdown
 exit
interface Port-channel13
 switchport mode trunk
 exit

 ! Enlace Troncal hacia MSW9 (Redacción Digital)
interface FastEthernet0/24
 switchport mode trunk
 exit

! Termino y guardo
end
copy running-config startup-config
```

##### 5.1.2.5 MSW5
- **Conexión 1:** Puertos 22-24 a SERVIDOR (LACP)
- **Conexión 2:** Puertos 7-9 a MSW4 (PAgP)
- **Conexión 3:** Puertos 10-12 a MSW2 (LACP)

```bash
enable
configure terminal
hostname MSW5

! Configuro el cliente
vtp mode client
vtp domain C2_FIUComm
vtp password proyecto12025

! Lo configuro en LACP
interface range FastEthernet0/22 - 24
 shutdown
 channel-protocol lacp
 channel-group 6 mode active
 no shutdown
 exit
interface Port-channel6
 switchport mode trunk
 exit

!  EtherChannel hacia MSW4 (PAgP)
interface range FastEthernet0/7 - 9
 shutdown
 channel-protocol pagp
 channel-group 13 mode desirable
 no shutdown
 exit
interface Port-channel13
 switchport mode trunk
 exit

! EtherChannel hacia MSW2 (LACP)
interface range FastEthernet0/10 - 12
 shutdown
 channel-protocol lacp
 channel-group 11 mode active
 no shutdown
 exit
interface Port-channel11
 switchport mode trunk
 exit

! Termino y guardo
end
copy running-config startup-config
```

##### 5.1.2.6 MSW6
- **Conexión 1:** Puertos 19-21 a SERVIDOR (LACP)
- **Conexión 2:** Puertos 4-6 a SERVIDOR (PAgP)
- **Conexión 3:** Puertos 22-24 a MSW1 (LACP)

```bash
enable
configure terminal
hostname MSW6

! Configuro el cliente
vtp mode client
vtp domain C2_FIUComm
vtp password proyecto12025

! Lo configuro en LACP
interface range FastEthernet0/19 - 21
 shutdown
 channel-protocol lacp
 channel-group 5 mode active
 no shutdown
 exit
interface Port-channel5
 switchport mode trunk
 exit

! EtherChannel hacia MSW3 (PAgP)
interface range FastEthernet0/4 - 6
 shutdown
 channel-protocol pagp
 channel-group 12 mode desirable
 no shutdown
 exit
interface Port-channel12
 switchport mode trunk
 exit

! EtherChannel hacia MSW1 (LACP)
interface range FastEthernet0/22 - 24
 shutdown
 channel-protocol lacp
 channel-group 10 mode active
 no shutdown
 exit
interface Port-channel10
 switchport mode trunk
 exit

! Termino y guardo
end
copy running-config startup-config
```

##### 5.1.2.7 Conexiones entre los Switches Cliente

   Switch | Puerto en Switch | Protocolo | Conexión a Switch |
 |--------|------------------|-----------|-------------------|
 | MSW4   | FastEthernet 7-9 | PAgP      | MSW5, puertos 7-9 |
 | MSW5   | FastEthernet 10-12 | LACP    | MSW2, puertos 10-12 |
 | MSW3   | FastEthernet 4-6 | PAgP      | MSW6, puertos 4-6 |
 | MSW6   | FastEthernet 22-24 | LACP    | MSW1, puertos 22-24 |


### 5.2 Gerencia

A continuación se listan las configuraciones de los switches de esta area.

#### 5.2.1 Switch MSW10

```bash
enable
configure terminal
hostname MSW10

! Configuración VTP (Modo Cliente)
vtp mode client
vtp domain C2_FIUComm
vtp password proyecto12025

! Configuración de Uplinks Troncales hacia el Backbone 
interface FastEthernet0/21
 switchport mode trunk
 exit
interface FastEthernet0/20
 switchport mode trunk
 exit

! Configuración de Downlink Troncal hacia Switches de Acceso
interface FastEthernet0/1
 switchport mode trunk
 exit
 
! Guardar Configuración
end
copy running-config startup-config
```

#### 5.2.2 Switch SW15

```bash
enable
configure terminal
hostname SW15

! Configuración VTP (Modo Cliente)
vtp mode client
vtp domain C2_FIUComm
vtp password proyecto12025

! Enlaces Troncales 
interface FastEthernet0/24 ! Uplink a MSW10
 switchport mode trunk
 exit
interface FastEthernet0/1 ! Downlink a SW14
 switchport mode trunk
 exit
interface FastEthernet0/2 ! Downlink a SW16
 switchport mode trunk
 exit

! Puerto de Acceso 
interface FastEthernet0/3 ! PC-PT RD8
 switchport mode access
 switchport access vlan 10
 spanning-tree portfast
 exit
 
! Guardar Configuración
end
copy running-config startup-config
```

#### 5.2.3 Switch SW14

```bash
enable
configure terminal
hostname SW14

! Configuración VTP (Modo Cliente) 
vtp mode client
vtp domain C2_FIUComm
vtp password proyecto12025

! Enlaces Troncales 
interface FastEthernet0/24 ! Uplink a SW15
 switchport mode trunk
 exit
interface FastEthernet0/1 ! Downlink a SW13
 switchport mode trunk
 exit

! Puertos de Acceso 
interface FastEthernet0/2 ! Laptop-PT S1
 switchport mode access
 switchport access vlan 40
 spanning-tree portfast
 exit
interface FastEthernet0/3 ! PC-PT IT5
 switchport mode access
 switchport access vlan 30
 spanning-tree portfast
 exit
 
! Guardar Configuración
end
copy running-config startup-config
```

#### 5.2.4 Switch SW13

```bash
enable
configure terminal
hostname SW13

! Configuración VTP (Modo Cliente)
vtp mode client
vtp domain C2_FIUComm
vtp password proyecto12025

! Enlace Troncal
interface FastEthernet0/24 ! Uplink a SW14
 switchport mode trunk
 exit

! Puerto de Acceso
interface FastEthernet0/1 ! PC-PT AD6
 switchport mode access
 switchport access vlan 20
 spanning-tree portfast
 exit
 
! Guardar Configuración
end
copy running-config startup-config
```

#### 5.2.5 Switch SW16

```bash
enable
configure terminal
hostname SW16

! Configuración VTP (Modo Cliente)
vtp mode client
vtp domain C2_FIUComm
vtp password proyecto12025

! Enlaces Troncales
interface FastEthernet0/24 ! Uplink a SW15
 switchport mode trunk
 exit
interface FastEthernet0/1 ! Downlink a SW17
 switchport mode trunk
 exit

! Puerto de Acceso
interface FastEthernet0/3 ! Laptop-PT G1
 switchport mode access
 switchport access vlan 50
 spanning-tree portfast
 exit
 
! Guardar Configuración
end
copy running-config startup-config
```

#### 5.2.6 Switch SW17

```bash
enable
configure terminal
hostname SW17

! Configuración VTP (Modo Cliente)
vtp mode client
vtp domain C2_FIUComm
vtp password proyecto12025

! Enlace Troncal
interface FastEthernet0/24 ! Uplink a SW16
 switchport mode trunk
 exit

! Puertos de Acceso
interface FastEthernet0/1 ! PC-PT IT4
 switchport mode access
 switchport access vlan 30
 spanning-tree portfast
 exit
interface FastEthernet0/2 ! Laptop-PT AD7
 switchport mode access
 switchport access vlan 20
 spanning-tree portfast
 exit
 
! Guardar Configuración
end
copy running-config startup-config
```


#### 5.2.7 Conexión entre los Switches
   Switch | Puerto en Switch | Conexión a Switch | Puerto en Conexión |
 |--------|------------------|-------------------|--------------------|
 | MSW1   | fa21             | MSW10             | fa21               |
 | MSW2   | fa20             | MSW10             | fa20               |
 | SW15   | fa24             | MSW10             | fa1                |
 | SW15   | fa1              | SW14              | fa24               |
 | SW15   | fa2              | SW16              | fa24               |
 | SW16   | fa1              | SW17              | fa24               |
 | SW14   | fa1              | SW13              | fa24               |

### 5.3 Infraestructura IT

### 5.4 Análissis de Datos 



### 5.5 Redacción Digital

A continuación se listan las configuraciones de los switches de esta area.

#### 5.5.1 Switch MSW9
- 
```bash
enable
configure terminal
hostname MSW9

! Configuración VTP (Modo Cliente) 
vtp mode client
vtp domain C2_FIUComm
vtp password proyecto12025

! Configuración de Uplinks Troncales hacia el Backbone 
interface range GigabitEthernet0/1 - 2
 switchport mode trunk
 exit

! Configuración de Downlinks hacia Switches de Acceso
interface range FastEthernet0/1 - 2
 switchport mode trunk
 exit

! Configuración de Puerto de Acceso para PC-PT S3
interface FastEthernet0/3
 switchport mode access
 switchport access vlan 40
 spanning-tree portfast
 exit

! Guardar Configuración
end
copy running-config startup-config

```

#### 5.5.2 Switch SW18

```bash
enable
configure terminal
hostname SW18

! Configuración VTP (Modo Cliente)
vtp mode client
vtp domain C2_FIUComm
vtp password proyecto12025

!  Configuración del Enlace Troncal (Uplink) hacia MSW9 
interface FastEthernet0/2
 switchport mode trunk
 exit

! Configuración del Enlace Troncal (Downlink) hacia SW20
interface FastEthernet0/1
 switchport mode trunk
 exit

! Guardar Configuración 
end
copy running-config startup-config

```


#### 5.5.2 Switch SW19

```bash
enable
configure terminal
hostname SW19

! Configuración VTP (Modo Cliente) 
vtp mode client
vtp domain C2_FIUComm
vtp password proyecto12025

! Configuración del Enlace Troncal (Uplink) hacia MSW9
interface FastEthernet0/2
 switchport mode trunk
 exit

!  Configuración de Puertos de Acceso de Laptop-PT G2
interface FastEthernet0/1
 switchport mode access
 switchport access vlan 50
 spanning-tree portfast
 exit
 
! Apagamos el resto de puertos no usados
interface range FastEthernet0/3 - 24
 shutdown
 exit

! Guardar Configuración
end
copy running-config startup-config
```

#### 5.5.2 Switch SW20

```bash
enable
configure terminal
hostname SW20

! Configuración VTP (Modo Cliente)
vtp mode client
vtp domain C2_FIUComm
vtp password proyecto12025

! Configuración del Enlace Troncal (Uplink) hacia SW18 
interface FastEthernet0/3
 switchport mode trunk
 exit

! Puerto para PC-PT S2
interface FastEthernet0/1
 switchport mode access
 switchport access vlan 40
 spanning-tree portfast
 exit
 
! Puerto para Laptop-PT RD2
interface FastEthernet0/2
 switchport mode access
 switchport access vlan 10
 spanning-tree portfast
 exit
 
! Apagamos el resto de puertos no usados
interface range FastEthernet0/4 - 23
 shutdown
 exit

! Guardar Configuración
end
copy running-config startup-config

```


#### 5.5.4 Conexiones entre los Switches
   Switch | Puerto en Switch | Conexión a Switch | Puerto en Conexión |
 |--------|------------------|-------------------|--------------------|
 | MSW3   | FastEthernet 24  | MSW9              | GigabitEthernet 1  |
 | MSW4   | FastEthernet 24  | MSW9              | GigabitEthernet 2  |
 | SW18   | FastEthernet 2   | MSW9              | FastEthernet 1     |
 | SW18   | FastEthernet 1   | SW20              | Puerto 3           |
 | SW19   | FastEthernet 2   | MSW9              | FastEthernet 2     |

