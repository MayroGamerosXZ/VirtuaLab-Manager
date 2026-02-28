# Requirements & Backlog

**Enlace al Tablero de Gestión:** [Reemplaza esto con el link a tu tablero de GitHub Projects, Jira o Trello]

## Lista de Historias de Usuario (Backlog)
1. **US01:** Autenticación de usuarios *(Must)*
2. **US02:** Solicitar nueva Máquina Virtual *(Must)*
3. **US03:** Visualizar listado y estado de VMs asignadas *(Must)*
4. **US04:** Aprobar/Rechazar solicitudes (Admin) *(Should)*
5. **US05:** Encender/Apagar VM desde el dashboard *(Should)*
6. **US06:** Notificaciones por correo del estado de la solicitud *(Could)*
7. **US07:** Gráficas de consumo de recursos en tiempo real *(Could)*
8. **US08:** Módulo de cálculo de costos por uso de hardware *(Won't)*

## Criterios de Aceptación (Given/When/Then)

**US02: Solicitar nueva Máquina Virtual (Must)**
* **Given** que el usuario está autenticado y se encuentra en la pantalla "Nueva Solicitud"
* **When** llena el formulario seleccionando el SO, la cantidad de RAM (ej. hasta 16GB) y núcleos de CPU, y hace clic en "Enviar"
* **Then** el sistema registra la solicitud con estado "Pendiente" y muestra un mensaje de confirmación al usuario.
* **Criterio extra:** El sistema debe validar que los campos de recursos no superen los límites de cuota del usuario.

**US03: Visualizar listado de VMs asignadas (Must)**
* **Given** que el usuario tiene al menos una VM aprobada y vinculada a su cuenta
* **When** navega a la sección "Mis Entornos"
* **Then** visualiza una tabla con el Nombre de la VM, Dirección IP y su Estado actual (Ejecutándose / Detenida).
* **Criterio extra:** La tabla debe poder filtrarse por el estado de la máquina.

## MVP Rationale
El MVP se centra exclusivamente en las historias con prioridad *Must* porque representan el núcleo operativo imprescindible del sistema. Sin autenticación (US01), no hay un entorno seguro; sin la capacidad de definir y solicitar recursos de hardware (US02) y sin poder ver qué máquinas se han asignado (US03), la plataforma carece de utilidad. Las funcionalidades *Should* y *Could*, como el control de encendido remoto o las gráficas, aportan gran valor y completan la experiencia, pero en la fase inicial la provisión y revisión pueden gestionarse manualmente por detrás. Lo clasificado como *Won't* queda descartado para esta iteración debido a su complejidad técnica y desviación del objetivo principal.
