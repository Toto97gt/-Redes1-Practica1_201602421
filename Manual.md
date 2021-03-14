# Manual de construcción y configuración

- [Manual de construcción y configuración](#manual-de-construcción-y-configuración)
  - [Integrantes](#integrantes)
  - [Configuración](#configuración)
    - [Topología 1](#topología-1)
      - [Distribución de pc's en topología 1](#distribución-de-pcs-en-topología-1)
      - [Configuración de ethernet switch](#configuración-de-ethernet-switch)
    - [Topología 2](#topología-2)
      - [Distribución de pc's en topología 2](#distribución-de-pcs-en-topología-2)
    - [VPN](#vpn)
    - [Máquinas virtuales](#máquinas-virtuales)

## Integrantes

|   Carné   | Nombre                                |
| :-------: | ------------------------------------- |
| 201020831 | Marco Antonio Fidencio Chávez Fuentes |
| 201602421 | Diego Alejandro Vasquez               |
| 201612331 | José Orlando Wannan Escobar           |

## Configuración

### Topología 1

![Topologia 1](Topologia1.png)

Se utilizaron 3 Ethernet switch y 3 VPCS obtenidos desde GNS3 así como también 3 instancias de VM obtenidas desde VMWare. Todas las pc's conectadas en esta topología son clientes y consumirán una página web de su respectivo departamento ubicada en la topología 2.

#### Distribución de pc's en topología 1

| VIRTUAL | HOST          | SWITCH  |   DIRECCIÓN IP   |   GATEWAY    |
| :-----: | ------------- | ------- | :--------------: | :----------: |
|   SI    | INFORMATICA1  | SWITCH1 | 192.168.29.15/24 | 192.168.29.1 |
|   NO    | INFORMATICA2  | SWITCH3 | 192.168.29.30/24 | 192.168.29.1 |
|   SI    | VENTAS1       | SWITCH4 | 192.168.39.15/24 | 192.168.39.1 |
|   NO    | VENTAS2       | SWITCH3 | 192.168.39.30/24 | 192.168.39.1 |
|   NO    | CONTABILIDAD1 | SWITCH1 | 192.168.49.15/24 | 192.168.49.1 |
|   SI    | CONTABILIDAD2 | SWITCH4 | 192.168.49.30/24 | 192.168.49.1 |

En todos los switches se configuró las 3 vlan para que tengan acceso las pc's y 2 puertos troncales para interconectarse entre switches

#### Configuración de ethernet switch

![Configurar switch](Configurar_EthernetSwitch.png)

En cada ethernet switch se configuraron los puertos troncales y de acceso para las vlan. Se configuraron los puertos 0 y 1 como puertos troncales y los puertos 2, 3 y 4 para acceso a las vlan 10, 20 y 30 respectivamente.

Luego, cada pc se conectó a su respectivo puerto en cada switch para poder acceder a su respectiva red. Para esto se le definieron sus respectivas dirección ip con el gateway definido para cada vlan.

```bash
# Configuración en pc 1 de la vlan informatica
ip 192.168.29.15/24 192.168.29.1

# Comprobar conexión en la vlan
ping 192.168.29.30
```

### Topología 2

![Topologia 1](Topologia1.png)

#### Distribución de pc's en topología 2

| VIRTUAL | HOST | SWITCH | DIRECCIÓN IP | GATEWAY |
| :-----: | ---- | ------ | :----------: | :-----: |
|         |      |        |              |         |
|         |      |        |              |         |
|         |      |        |              |         |
|         |      |        |              |         |
|         |      |        |              |         |
|         |      |        |              |         |
|         |      |        |              |         |
|         |      |        |              |         |

### VPN

### Máquinas virtuales
