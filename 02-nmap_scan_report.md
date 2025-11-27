# Nmap Scan Report — Lab 2 (Escaneo Selectivo y Análisis de Riesgos)

## 1. Introducción

Este laboratorio tiene como objetivo practicar el uso de **Nmap** para realizar un escaneo parcial y controlado de un host dentro de un entorno educativo ficticio. El propósito es aprender a interpretar resultados, identificar servicios expuestos y comprender los riesgos potenciales asociados.

Todas las direcciones IP, versiones y servicios utilizados en este informe son **totalmente ficticios** y adaptados para uso académico.

---

## 2. Comando utilizado

Se escanearon únicamente puertos específicos con el fin de obtener información relevante sin necesidad de hacer un reconocimiento completo.

```bash
nmap -sV -p 22,80,443,3306 192.168.100.50
```

### Parámetros usados

* **-sV** → Detección de versiones.
* **-p** → Escaneo de puertos definidos manualmente.
* **22,80,443,3306** → SSH, HTTP, HTTPS, MySQL.
* **192.168.100.50** → Dirección IP ficticia de laboratorio.

---

## 3. Resultados del escaneo (CONFIDENCIALIZADO)

```
PORT     STATE    SERVICE   VERSION
22/tcp   open     ssh       OpenSSH 7.9p1 (protocol 2.0)
80/tcp   open     http      Apache httpd 2.4.38
443/tcp  open     https     Apache httpd 2.4.38
3306/tcp open     mysql     MySQL 5.7.29
```

Estos resultados fueron generados de manera sintética para fines formativos.

---

## 4. Análisis de servicios detectados

### 🔹 Puerto 22 — SSH

* Servicio detectado: **OpenSSH 7.9** (ficticio).
* Permite acceso remoto administrativo seguro.

**Puntos a evaluar:**

* Políticas de autenticación.
* Posibles ataques de fuerza bruta.
* Restricciones de usuario y firewall.

---

### 🔹 Puerto 80 / 443 — Apache Web Server

* Versión: **Apache 2.4.38** (ficticia).
* Puerto **80** ofrece contenido sin cifrado.
* Puerto **443** permite tráfico cifrado por TLS.

**Elementos a revisar:**

* Certificados SSL/TLS.
* Headers de seguridad (HSTS, CSP, X-Frame-Options).
* Posibles endpoints sensibles.

---

### 🔹 Puerto 3306 — MySQL

* Base de datos accesible desde la red interna.

**Evaluaciones sugeridas:**

* Permisos de acceso remoto.
* Políticas de contraseñas.
* Revisión de usuarios y roles.

---

## 5. Riesgos Potenciales Identificados

A continuación se enumeran riesgos asociados a configuraciones típicas en infraestructuras reales (aplicados conceptualmente a este laboratorio):

### ⚠ Exposición innecesaria de servicios

Un atacante podría:

* Identificar servicios disponibles.
* Realizar reconocimiento avanzado.
* Ejecutar ataques dirigidos según la superficie expuesta.

### ⚠ Versiones detectables

La detección de versiones permite:

* Buscar CVEs asociadas.
* Identificar vulnerabilidades conocidas.
* Atacar configuraciones obsoletas.

### ⚠ Credenciales débiles o mal gestionadas

Servicios como MySQL o SSH pueden ser vulnerables si:

* Se usan contraseñas simples.
* Hay usuarios por defecto.
* No existen límites de intentos o MFA.

### ⚠ Configuraciones inseguras

Casos comunes:

* MySQL escuchando en todas las interfaces.
* Apache sin headers de seguridad.
* SSH permitiendo autenticación por contraseña.

---

## 6. Conclusión

Este laboratorio permitió:

* Realizar un escaneo selectivo con Nmap.
* Analizar servicios expuestos de forma segura.
* Identificar riesgos comunes sin exponer información real.
* Documentar hallazgos de forma profesional.

Este formato es ideal para un portfolio técnico, mostrando:

* Buenas prácticas.
* Conocimientos de enumeración.
* Capacidad de análisis.
