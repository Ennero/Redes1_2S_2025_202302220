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
    - [5.1 Switch Backbone (SW-BB)](#51-switch-backbone-sw-bb)
    - [5.2 Switch Gerencia (SW-Gerencia)](#52-switch-gerencia-sw-gerencia)
    - [5.3 Configuración de EtherChannel](#53-configuración-de-etherchannel)
  - [6. Pruebas y Verificación](#6-pruebas-y-verificación)
    - [6.1 Pruebas de Conectividad (Ping)](#61-pruebas-de-conectividad-ping)
    - [6.2 Verificación de VTP](#62-verificación-de-vtp)
    - [6.3 Verificación de STP](#63-verificación-de-stp)
    - [6.4 Verificación de EtherChannel](#64-verificación-de-etherchannel)



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

### 5.1 Switch Backbone (SW-BB)
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
### 5.2 Switch Gerencia (SW-Gerencia)




### 5.3 Configuración de EtherChannel



## 6. Pruebas y Verificación


### 6.1 Pruebas de Conectividad (Ping)



### 6.2 Verificación de VTP

### 6.3 Verificación de STP





### 6.4 Verificación de EtherChannel



