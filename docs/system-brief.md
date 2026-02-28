# System Brief: VirtuaLab Manager

## Visión
Proveer una plataforma centralizada y autogestionada donde los usuarios puedan solicitar entornos virtualizados con configuraciones de hardware específicas, reduciendo el cuello de botella administrativo en la asignación de recursos.

## Alcance (Scope)
* Autenticación de usuarios y roles (Estudiante/Administrador).
* Formulario de solicitud de Máquinas Virtuales (OS, RAM, CPU).
* Tablero de visualización del estado de las VMs asignadas (Activa/Apagada).
* Panel de administración para aprobar o rechazar solicitudes.

## Fuera de Alcance (No-scope)
* Facturación o cobro por uso de recursos.
* Acceso a la consola de la VM directamente desde el navegador (VNC/RDP web).
* Instalación automatizada de software de terceros dentro del sistema operativo huésped.

## Diagrama de Contexto
```mermaid
graph TD
    A[Usuario/Estudiante] -->|Solicita y monitorea VMs| B(VirtuaLab Web App)
    B -->|Envía aprobaciones| C[Administrador]
    B -->|API Requests| D{Hipervisor - Proxmox/VirtualBox}
    D -->|Despliega| E[Máquina Virtual Asignada]
