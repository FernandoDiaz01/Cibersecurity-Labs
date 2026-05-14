# Fortalecimiento de Seguridad Digital – Sala de Monitoreo

## Descripción del Proyecto
Este proyecto detalla la intervención técnica realizada en la infraestructura de red de una empresa de seguridad física para mitigar vulnerabilidades críticas. El objetivo principal fue transicionar desde una arquitectura de red plana y expuesta hacia un modelo segmentado con controles de acceso granulares.

## 1. Diagnóstico de la Infraestructura Inicial
Se identificó una red inalámbrica de uso general donde coexistían sin restricciones:
* **Activos de Operación Crítica:** Estación de monitoreo con software de trackeo vehicular y Smart TVs de visualización.
* **Dispositivos de Terceros:** Notebooks personales de empleados y otros dispositivos externos con acceso total a la LAN.

## 2. Análisis de Riesgos y Vulnerabilidades
La falta de controles de acceso y aislamiento exponía a la organización a:
* **Contaminación Cruzada:** Propagación de malware desde dispositivos de empleados hacia sistemas de gestión vehicular.
* **Saturación de Red:** Latencia en reportes críticos debido al consumo de ancho de banda por actividades no laborales (streaming/descargas).
* **Movimiento Lateral:** Visibilidad técnica y potencial acceso no autorizado a los equipos de monitoreo por parte de cualquier usuario en la red.

## 3. Implementación Técnica (Solución)
Se aplicó un esquema de **Segmentación Lógica** optimizando el hardware existente para una solución de costo cero:

### Segmentación de Red (VLANs)
* **VLAN Crítica (Operaciones):** Entorno blindado para la PC de trackeo y monitores, con prioridad de tráfico y visibilidad restringida.
* **VLAN de Invitados (Aislada):** Red estanca para dispositivos personales, permitiendo únicamente salida a Internet sin acceso a los activos internos.

### Hardening y Auditoría
* **Endurecimiento de WiFi:** Actualización de protocolos de cifrado y aplicación de políticas de contraseñas complejas.
* **Monitoreo Proactivo:** Integración de la herramienta **Sentinel** para la identificación de activos y detección de puntos ciegos en la red.

## 4. Alineación con Estándares
El proyecto se diseñó bajo los controles de la norma **ISO/IEC 27001**, fortaleciendo la postura de seguridad organizacional y asegurando la continuidad operativa del servicio de seguridad física.

## Tecnologías Utilizadas
* **Networking:** Segmentación de Red, VLANs, Firewalling.
* **Seguridad:** Hardening de Redes, ISO 27001.
* **Auditoría:** Sentinel (Asset Discovery).

## 📹 Demostración de Auditoría

<video src="img/demo-sentinel.mp4" width="100%" controls></video>