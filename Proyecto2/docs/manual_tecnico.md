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
    - [3.1 DIGA](#31-diga)
    - [3.2 Biblioteca](#32-biblioteca)
    - [3.3 Edificio T4](#33-edificio-t4)
    - [3.4 Edificio S11](#34-edificio-s11)
    - [3.5 Edificio S12](#35-edificio-s12)
    - [3.6 BACKBONE](#36-backbone)
  - [4. Tabla de Direccionamiento IP](#4-tabla-de-direccionamiento-ip)
    - [4.1 Direcciones de dispositivos](#41-direcciones-de-dispositivos)
    - [4.2 Direcciones de puertos de enlace](#42-direcciones-de-puertos-de-enlace)
  - [5. Subnetting](#5-subnetting)
    - [5.1 DIGA](#51-diga)
    - [5.2 Biblioteca](#52-biblioteca)
    - [5.3 Edificio T4](#53-edificio-t4)
    - [5.4 Edificio S11](#54-edificio-s11)
    - [5.5 Edificio S12](#55-edificio-s12)
    - [5.6 BACKBONE](#56-backbone)
  - [6. Configuraciones de Dispositivos](#6-configuraciones-de-dispositivos)
    - [6.1 DIGA](#61-diga)
      - [6.1.1 Conexiones entre los switches](#611-conexiones-entre-los-switches)
      - [6.1.2 Conexiones a dispositivos finales](#612-conexiones-a-dispositivos-finales)
    - [6.2 Biblioteca](#62-biblioteca)
      - [6.2.1 Conexiones entre los switches](#621-conexiones-entre-los-switches)
      - [6.2.2 Conexiones a dispositivos finales](#622-conexiones-a-dispositivos-finales)
    - [6.3 Edificio T4](#63-edificio-t4)
      - [6.3.1 Conexiones entre los switches](#631-conexiones-entre-los-switches)
      - [6.3.2 Conexiones a dispositivos finales](#632-conexiones-a-dispositivos-finales)
    - [6.4 Edificio S11](#64-edificio-s11)
      - [6.4.1 Conexiones entre los switches](#641-conexiones-entre-los-switches)
      - [6.4.2 Conexiones a dispositivos finales](#642-conexiones-a-dispositivos-finales)
    - [6.5 Edificio S12](#65-edificio-s12)
      - [6.5.1 Conexiones entre los switches](#651-conexiones-entre-los-switches)
      - [6.5.2 Conexiones a dispositivos finales](#652-conexiones-a-dispositivos-finales)
    - [6.6 BACKBONE](#66-backbone)
      - [6.6.1 RIP (Routing Information Protocol)](#661-rip-routing-information-protocol)
      - [6.6.2 OSPF (Open Shortest Path First)](#662-ospf-open-shortest-path-first)
      - [6.6.3 EIGRP (Enhances Interior Gateway Routing Protocol)](#663-eigrp-enhances-interior-gateway-routing-protocol)
      - [6.6.4 Rutas Estáticas](#664-rutas-estáticas)



## 1. Objetivos

### 1.1 Objetivo General
 Diseñar, configurar y simular una infraestructura de red inter-edificios para el campus central de la Universidad de San Carlos (NetUSAC) utilizando Cisco Packet Tracer. El diseño busca garantizar una comunicación eficiente, segura y redundante entre cinco edificios clave, implementando segmentación de red, protocolos de enrutamiento avanzado y alta disponibilidad.

### 1.2 Objetivos Específicos
* **Segmentar** la red de cada edificio en VLANs para separar el tráfico de distintas áreas (Estudiantes, Docentes, Administración, etc.).
* **Implementar** un esquema de direccionamiento IP jerárquico utilizando VLSM y FLSM para optimizar el uso del espacio de direcciones.
* **Configurar** enrutamiento Inter-VLAN para permitir la comunicación controlada entre las diferentes VLANs de la topología.
* **Establecer** la interconexión del backbone de la red mediante protocolos de enrutamiento dinámico (RIP, OSPF, EIGRP) y rutas estáticas.
* **Asegurar** la alta disponibilidad de la red implementando protocolos de redundancia de primer salto como HSRP y VRRP.
* **Implementar** políticas de seguridad básicas mediante Listas de Control de Acceso (ACLs) para filtrar el tráfico entre VLANs.
* **Validar** la conectividad completa de la red y el correcto funcionamiento de los protocolos implementados tanto en la simulación como en la implementación física.

---

## 2. Alcance del Proyecto

### 2.1 Inclusiones
* El diseño, configuración y validación se realizan principalmente en el simulador **Cisco Packet Tracer**.
* La topología abarca la interconexión de **cinco edificios**: Biblioteca Central, Edificio T4, Edificio S11, Edificio S12 y DIGA.
* Configuración de tecnologías de Capa 2 y Capa 3, incluyendo VLANs, VTP, enrutamiento Inter-VLAN, HSRP, VRRP, RIP, OSPF, EIGRP, rutas estáticas y redistribución de rutas.
* Implementación de una **parte física** de la topología para validar la configuración de VLANs en equipos reales.
* Asignación de direccionamiento IP y configuración de todos los dispositivos de red mediante la **Interfaz de Línea de Comandos (CLI)**.

### 2.2 Exclusiones
* La conexión de la red del campus con redes externas como WAN o Internet.
* La implementación de mecanismos de seguridad avanzados más allá de las Listas de Control de Acceso (ACLs) estándar/extendidas.
* Configuración de servicios de red como DHCP, DNS o servidores web, a menos que sea estrictamente necesario para pruebas de conectividad.
* El uso de interfaces gráficas de usuario (GUI) para la configuración de los dispositivos.

---

## 3. Topología de Red
A continuación, se presenta el diagrama de la topología de red implementada en Cisco Packet Tracer para el proyecto NetUSAC. La red interconecta cinco edificios clave del campus central de la Universidad de San Carlos: Biblioteca Central, Edificio T4, Edificio S11, Edificio S12 y DIGA. La comunicación entre estos edificios se gestiona a través de un Backbone central, diseñado para garantizar la redundancia, la seguridad y un flujo de tráfico eficiente mediante enrutamiento avanzado.

### 3.1 DIGA

### 3.2 Biblioteca

### 3.3 Edificio T4

### 3.4 Edificio S11

### 3.5 Edificio S12


### 3.6 BACKBONE



## 4. Tabla de Direccionamiento IP

### 4.1 Direcciones de dispositivos


### 4.2 Direcciones de puertos de enlace



## 5. Subnetting

### 5.1 DIGA
Para este edificio se usa VLSM:
| HOSTS NECESARIOS | VLAN | OFICINA    | ID RED        | MASCARA           | WILDCARD     | PRIMER HOST    | ULTIMO HOST     | BROADCAST      | HOST. UTILIZABLES |
|-----------------|------|------------|---------------|-------------------|--------------|----------------|-----------------|----------------|------------------|
| 120             | 42   | Admin      | 192.168.20.0  | 255.255.255.128   | 0.0.0.127    | 192.168.20.1   | 192.168.20.126  | 192.128.20.127  | 126              |
| 20              | 32   | Vigilancia | 192.168.20.128| 255.255.255.224   | 0.0.0.31     | 192.128.20.129 | 192.168.20.158  | 192.168.20.159  | 30               |
| 5               | 22   | Docentes   | 192.168.20.160| 255.255.255.248   | 0.0.0.7      | 192.168.20.161 | 192.168.20.166  | 192.168.20.167  | 6                |
| 5               | 12   | Estudiantes| 192.168.20.168| 255.255.255.248   | 0.0.0.7      | 192.168.20.169 | 192.168.20.174  | 192.168.20.175  | 6                |

### 5.2 Biblioteca
Para este edificio se usa VLSM:

| HOSTS NECESARIOS | VLAN | OFICINA    | ID RED        | MASCARA           | WILDCARD     | PRIMER HOST    | ULTIMO HOST     | BROADCAST      | HOST. UTILIZABLES |
|-----------------|------|------------|---------------|-------------------|--------------|----------------|-----------------|----------------|------------------|
| 75              | 12   | Estudiantes| 192.158.20.0  | 255.255.255.128   | 0.0.0.127    | 192.158.20.1   | 192.158.20.126  | 192.158.20.127  | 126              |
| 30              | 32   | Vigilancia | 192.158.20.128| 255.255.255.224   | 0.0.0.31     | 192.158.20.129 | 192.158.20.158  | 192.158.20.159  | 30               |
| 25              | 52   | Biblioteca | 192.158.20.160| 255.255.255.224   | 0.0.0.31     | 192.158.20.161 | 192.158.20.190  | 192.158.20.191  | 30               |

### 5.3 Edificio T4

Para este edificio se usa VLSM:
| HOSTS NECESARIOS | VLAN | OFICINA    | ID RED        | MASCARA           | WILDCARD     | PRIMER HOST    | ULTIMO HOST     | BROADCAST      | HOST. UTILIZABLES | HOST UTILIZADOS | DESPERDICIO |
|-----------------|------|------------|---------------|-------------------|--------------|----------------|-----------------|----------------|------------------|----------------|-------------|
| 75              | 42   | Admin      | 172.16.20.0   | 255.255.255.128   | 0.0.0.127    | 172.16.20.1    | 172.16.20.126   | 172.16.20.127   | 126              | 1              | 125         |
| 60              | 12   | Estudiantes| 172.16.20.128 | 255.255.255.192   | 0.0.0.63     | 172.16.20.129  | 172.16.20.190   | 172.16.20.191   | 62               | 1              | 61          |
| 15              | 32   | Vigilancia | 172.16.20.192 | 255.255.255.224   | 0.0.0.31     | 172.16.20.193  | 172.16.20.222   | 172.16.20.223   | 30               | 1              | 29          |
| 12              | 52   | Biblioteca | 172.16.20.224 | 255.255.255.240   | 0.0.0.15     | 172.16.20.225  | 172.16.20.238   | 172.16.20.239   | 14               | 2              | 12          |
| 10              | 22   | Docentes   | 172.16.20.240 | 255.255.255.240   | 0.0.0.15     | 172.16.20.241  | 172.16.20.254   | 172.16.20.255   | 14               | 1              | 13          |


### 5.4 Edificio S11
Para este edificio se usa VLSM:
| HOSTS NECESARIOS | VLAN | OFICINA    | ID RED        | MASCARA           | WILDCARD     | PRIMER HOST    | ULTIMO HOST     | BROADCAST      | HOST. UTILIZABLES | HOST UTILIZADOS | DESPERDICIO |
|-----------------|------|------------|---------------|-------------------|--------------|----------------|-----------------|----------------|------------------|----------------|-------------|
| 100             | 12   | Estudiantes| 172.148.20.0  | 255.255.255.128   | 0.0.0.127    | 172.148.20.1   | 172.148.20.126  | 172.148.20.127  | 126              | 2              | 124         |
| 55              | 52   | Admin      | 172.148.20.128| 255.255.255.192   | 0.0.0.63     | 172.148.20.129 | 172.148.20.190  | 172.148.20.191  | 62               | 1              | 61          |
| 15              | 22   | Docentes   | 172.148.20.192| 255.255.255.224   | 0.0.0.31     | 172.148.20.193 | 172.148.20.222  | 172.148.20.223  | 30               | 2              | 28          |
| 10              | 32   | Vigilancia | 172.148.20.224| 255.255.255.240   | 0.0.0.15     | 172.148.20.225 | 172.148.20.238  | 172.148.20.239  | 14               | 1              | 13          |


### 5.5 Edificio S12
Para este edificio se usa VLSM:
| HOSTS NECESARIOS | VLAN | OFICINA    | ID RED        | MASCARA           | WILDCARD     | PRIMER HOST    | ULTIMO HOST     | BROADCAST      | HOST. UTILIZABLES | HOST UTILIZADOS | DESPERDICIO |
|-----------------|------|------------|---------------|-------------------|--------------|----------------|-----------------|----------------|------------------|----------------|-------------|
| 125             | 12   | Estudiantes| 192.128.20.0  | 255.255.255.128   | 0.0.0.127    | 192.128.20.1   | 192.128.20.126  | 192.128.20.127  | 126              | 2              | 124         |
| 35              | 22   | Docentes   | 192.128.20.128| 255.255.255.192   | 0.0.0.63     | 192.128.20.129 | 192.128.20.190  | 192.128.20.191  | 62               | 2              | 60          |
| 25              | 42   | Admin      | 192.128.20.192| 255.255.255.224   | 0.0.0.31     | 192.128.20.193 | 192.128.20.222  | 192.128.20.223  | 30               | 1              | 29          |
| 20              | 32   | Vigilancia | 192.128.20.224| 255.255.255.224   | 0.0.0.31     | 192.128.20.225 | 192.128.20.254  | 192.128.20.255  | 30               | 1              | 29          |

### 5.6 BACKBONE




## 6. Configuraciones de Dispositivos

### 6.1 DIGA


#### 6.1.1 Conexiones entre los switches
| Switch/Router | Puerto1 | Switch/Router2 | Puerto2 |
|--------------|---------|---------------|---------|
| SW6          | fa4     | SW5           | fa22    |
| SW5          | fa3     | SW4           | fa22    |
| SW4          | fa3     | SW3           | fa23    |
| MS2          | fa1     | SW6           | fa24    |
| MS2          | fa2     | SW5           | fa24    |
| MS2          | fa3     | SW4           | fa24    |
| MS1          | fa1     | SW5           | fa23    |
| MS1          | fa2     | SW4           | fa23    |
| MS1          | fa3     | SW3           | fa24    |
| firewall1    | gi1     | MS2           | fa24    |
| firewall1    | gi2     | MS1           | fa24    |


#### 6.1.2 Conexiones a dispositivos finales

| Switch/Router | Puerto en Switch | Dispositivo Final |
|--------------|------------------|-------------------|
| SW6          | fa1              | vigilancia2       |
| SW6          | fa2              | vigilancia3       |
| SW6          | fa3              | admin5            |
| SW5          | fa1              | admin4            |
| SW5          | fa2              | admin3            |
| SW4          | fa1              | admin2            |
| SW4          | fa2              | admin1            |
| SW3          | fa1              | admin Server      |
| SW3          | fa2              | estudiantes Server|
| SW3          | fa3              | docentes Server   |



### 6.2 Biblioteca


#### 6.2.1 Conexiones entre los switches
| Switch/Router | Puerto1 | Switch/Router2 | Puerto2 |
|--------------|---------|---------------|---------|
| MS0          | fa1     | SW0           | fa24    |
| MS0          | fa2     | Switch6       | fa24    |
| MS0          | fa3     | SW1           | fa24    |
| R1           | gi0     | MS0           | fa24    |
| R0           | gi0     | MS0           | fa23    |
| firewall2    | gi1     | R1            | gi1     |
| firewall2    | gi2     | R0            | gi1     |



#### 6.2.2 Conexiones a dispositivos finales

| Switch/Router | Puerto en Switch | Dispositivo Final |
|--------------|------------------|-------------------|
| SW0          | fa1              | vigilancia1       |
| SW0          | fa2              | biblioteca3        |
| Switch6      | fa1              | estudiantes3      |
| Switch6      | fa2              | biblioteca1        |
| SW1          | fa1              | estudiantes1      |
| SW1          | fa2              | estudiantes2      |



### 6.3 Edificio T4



#### 6.3.1 Conexiones entre los switches

| Switch/Router | Puerto1 | Switch/Router2 | Puerto2 |
|--------------|---------|---------------|---------|
| SW9          | fa3     | SW8           | fa23    |
| SW8          | fa3     | SW7           | fa23    |
| MS5          | fa1     | SW9           | fa24    |
| MS5          | fa2     | SW8           | fa24    |
| MS5          | fa3     | SW7           | fa24    |
| firewall3    | gi1     | MS5           | fa24    |

#### 6.3.2 Conexiones a dispositivos finales

| Switch/Router | Puerto en Switch | Dispositivo Final |
|--------------|------------------|-------------------|
| SW9          | fa1              | vigilancia4       |
| SW9          | fa2              | docentes2         |
| SW8          | fa1              | estudiantes10     |
| SW8          | fa2              | admin6            |
| SW7          | fa1              | biblioteca5        |
| SW7          | fa2              | biblioteca4        |




### 6.4 Edificio S11



#### 6.4.1 Conexiones entre los switches
| Switch/Router | Puerto1 | Switch/Router2 | Puerto2 |
|--------------|---------|---------------|---------|
| SW10         | fa3     | SW11          | fa22    |
| SW11         | fa3     | SW12          | fa24    |
| R10          | gi0     | SW1           | fa24    |
| R11          | gi0     | MS0           | fa23    |
| firewall4    | gi1     | R10           | gi1     |
| firewall4    | gi2     | R11           | gi1     |



#### 6.4.2 Conexiones a dispositivos finales
| Switch/Router | Puerto en Switch | Dispositivo Final |
|--------------|------------------|-------------------|
| SW10         | fa1              | admin7            |
| SW10         | fa2              | docentes3         |
| SW11         | fa1              | docentes4         |
| SW11         | fa2              | estudiantes4      |
| SW12         | fa1              | estudiantes5      |
| SW12         | fa2              | vigilancia5       |




### 6.5 Edificio S12


#### 6.5.1 Conexiones entre los switches

| Switch/Router | Puerto1 | Switch/Router2 | Puerto2 |
|--------------|---------|---------------|---------|
| SW13         | fa1     | SW15          | fa24    |
| SW13         | fa2     | SW16          | fa24    |
| SW13         | fa3     | SW17          | fa24    |
| SW14         | fa1     | SW15          | fa23    |
| SW14         | fa2     | SW16          | fa23    |
| SW14         | fa3     | SW17          | fa23    |
| MS9          | fa1     | SW13          | fa24    |
| MS9          | fa2     | SW14          | fa24    |
| MS7          | fa1     | MS9           | fa24    |
| MS8          | fa1     | MS9           | fa23    |
| firewall5    | gi1     | MS7           | fa24    |
| firewall5    | gi2     | MS8           | fa24    |


#### 6.5.2 Conexiones a dispositivos finales
| Switch/Router | Puerto en Switch | Dispositivo Final |
|--------------|------------------|-------------------|
| SW15         | fa1              | vigilancia6       |
| SW15         | fa2              | estudiantes7      |
| SW16         | fa1              | docentes6         |
| SW16         | fa2              | estudiantes6      |
| SW17         | fa1              | docentes5         |
| SW17         | fa2              | admin8            |



### 6.6 BACKBONE


#### 6.6.1 RIP (Routing Information Protocol)
| Switch/Router (DCE) | Puerto1 | Switch/Router2 | Puerto2 |
|-------------------|---------|---------------|---------|
| R3                | gi0     | firewall1     | gi8     |
| R3                | gi1     | firewall2     | gi8     |
| R4                | serial0 | R3            | serial0 |
| R4                | serial1 | R2            | serial1 |
| R2                | serial1 | R3            | serial1 |
| R5                | gi0     | R4            | gi1     |



#### 6.6.2 OSPF (Open Shortest Path First)
| Switch/Router | Puerto1 | Switch/Router2 | Puerto2 |
|--------------|---------|---------------|---------|
| R7           | gi0     | R8            | g1      |
| R8           | g0      | R9            | gi1     |
| R9           | fa6     | firewall5     | gi8     |
| R9           | fa7     | firewall4     | gi8     |


#### 6.6.3 EIGRP (Enhances Interior Gateway Routing Protocol)
| Switch/Router | Puerto1 | Switch/Router2 | Puerto2 |
|--------------|---------|---------------|---------|
| MS4          | fa1-3   | MS3           | fa1-3   |
| MS4          | fa4-6   | MS6           | fa4-6   |
| MS4          | gi1     | R6            | gi1     |
| MS3          | fa7-9   | MS6           | fa7-9   |
| MS3          | gi1     | R5            | gi1     |
| MS6          | gi1     | R7            | gi1     |



#### 6.6.4 Rutas Estáticas

| Switch/Router | Puerto1 | Switch/Router2 | Puerto2 |
|--------------|---------|---------------|---------|
| R6           | gi0     | firewall4     | gi8     |








