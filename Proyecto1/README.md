# Manual técnico
---
#### Diego Andres Huite Alvarez - 202003585
#### Dayana Alejandra Reyes Rodríguez - 202002364 
---

## Resumen de direcciones ip y vlan:

| Nombre del equipo | Departamento         | VLAN | Dirección IP   |
|-------------------|----------------------|------|----------------|
| S_CONTABILIDAD    | Contabilidad         | 19   | 192.168.19.2   |
| CONTABILIDAD_1    | Contabilidad         | 19   | 192.168.19.1   |
| CONTABILIDAD_2    | Contabilidad         | 19   | 192.168.19.3   |
| SECRETARIA        | Secretaría           | 29   | 192.168.29.3   |
| SECRETARIA1       | Secretaría           | 29   | 192.168.29.1   |
| SECRETARIA2       | Secretaría           | 29   | 192.168.29.2   |
| S_RRHH            | Recursos humanos     | 39   | 192.168.39.4   |
| RRHH              | Recursos humanos     | 39   | 192.168.39.3   |
| RRHH1             | Recursos humanos     | 39   | 192.168.39.1   |
| RRHH2             | Recursos humanos     | 39   | 192.168.39.2   |
| S_IT              | IT                   | 49   | 192.168.49.3   |
| IT_1              | IT                   | 49   | 192.168.49.1   |
| IT_2              | IT                   | 49   | 192.168.49.2   |

---
## Topologías:
- **Centro administrativo:**
  
  ![image](https://github.com/Dgo45921/Redes1_202003585/assets/80992782/55136e3f-4da5-4e7e-af9c-9ebc773a8469)

- **Backbone:**


  ![image](https://github.com/Dgo45921/Redes1_202003585/assets/80992782/bb55b3bf-ee93-4201-9385-d6c897117bfa)


- **Área de trabajo:**


  ![image](https://github.com/Dgo45921/Redes1_202003585/assets/80992782/dbc04c48-6998-4118-85a6-5c76cfb57e0b)

---
## Comandos utilizados:

### switches
- **Configurar tipo de switch:**
  ```console
  enable
  configure terminal
  vtp mode client|server|transparent
  exit
  wr
  ```
  
- **Configurar dominio y password:**
  ```console
  enable
  configure terminal
  vtp domain P12
  vtp password usac
  exit
  wr
  ```

- **Configurar modo truncal (2960-24TT) :**
  ```console
  enable
  configure terminal
  interface fastEthernet 0/1
  switchport mode trunk
  switchport trunk allowed vlan all
  exit
  exit
  wr
  ```

  - **Configurar modo acceso (2960-24TT):**
  ```console
  enable
  configure terminal
  interface fastEthernet 0/1
  switchport mode access
  switchport access vlan 20
  no shutdown
  exit
  exit
  wr
  ```

- **Configurar modo truncal (3560-24PS) :**
  ```console
  enable
  configure terminal
  interface fastEthernet 0/1
  switchport trunk encapsulation dot1q
  switchport mode trunk
  switchport trunk allowed vlan all
  exit
  exit
  wr
  ```

- **Configurar tipo de STP:**
  ```console
  enable 
  configure terminal
  spanning-tree mode pvst | rapid-pvst
  exit 
  wr
  ```

- **Configurar switch como bridge root:**
  ```console
  enable 
  configure terminal
  spanning-tree vlan 1 root primary
  exit 
  wr
  ```
---
## Ping entre IT_2 a IT_1:

  ![image](https://github.com/Dgo45921/Redes1_202003585/assets/80992782/1b8e36e8-13c2-4745-a87c-d4a0276dd5cd)

## Ping entre CONTABILIDAD2 a S_CONTABILIDAD:
  ![image](https://github.com/Dgo45921/Redes1_202003585/assets/80992782/7cee64f4-376d-4fa6-8605-a5a192d67f40)

  
