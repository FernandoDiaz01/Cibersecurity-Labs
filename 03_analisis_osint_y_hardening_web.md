# 🛡️ Laboratorio de Análisis de Superficie de Ataque (SOC Trainee)

> **Perfil:** SOC Trainee / Junior  
> **Contexto:** Laboratorio educativo – análisis pasivo y entorno controlado  
> **Estado:** Apto para publicación pública (información anonimizada)

---

## 📌 Descripción del proyecto

Este proyecto documenta un **laboratorio práctico de ciberseguridad** enfocado en el **análisis inicial de superficie de ataque**, aplicando una mirada **SOC (Security Operations Center)**.

Se realizaron tareas de **OSINT, enumeración pasiva, revisión de configuraciones web y análisis de encabezados HTTP/TLS**, junto con prácticas de **enumeración de subdominios en un entorno vulnerable controlado (Metasploitable)**.

Toda la información sensible fue **anonimizada** para permitir su publicación en un repositorio público.

---

## 🎯 Objetivos

- Comprender cómo un SOC identifica **riesgos de configuración** en activos web
- Practicar **lectura e interpretación de WHOIS**
- Diferenciar **WHOIS vs Threat Intelligence**
- Analizar **headers HTTP/HTTPS y TLS**
- Detectar **malas prácticas de seguridad web** (HTTP, TLS legacy, certificados)
- Enumerar subdominios en **entornos de laboratorio**
- Documentar hallazgos de forma **ética y profesional**

---

## 🧰 Herramientas utilizadas

- **Kali Linux** (entorno de trabajo)
- **WHOIS / NIC.ar / ICANN** (OSINT)
- **Knockpy** (enumeración pasiva de dominios y subdominios)
- **curl** (inspección de encabezados HTTP)
- **Metasploitable** (máquina vulnerable de laboratorio)

---

## 🔍 Metodología

### 1️⃣ Recolección OSINT
- Consulta WHOIS para identificar:
  - Registrador
  - Fechas
  - Servidores DNS
- Interpretación desde una perspectiva SOC

### 2️⃣ Diferencia WHOIS vs Threat Intelligence

| WHOIS | Threat Intelligence |
|------|--------------------|
| Información pública | Información contextual de amenazas |
| Datos de registro | Indicadores de compromiso |
| No indica riesgo | Evalúa reputación y actividad maliciosa |

---

### 3️⃣ Enumeración de directorios (DIRB)

Como parte del reconocimiento inicial, se utilizó **DIRB** sobre una **aplicación vulnerable de laboratorio (Mutillidae)** alojada en una máquina virtual.

- Se revisó previamente la documentación oficial mediante `man dirb`, identificando la sección **SYNOPSIS**, que describe la forma correcta de uso de la herramienta.
- DIRB realizó fuerza bruta de rutas utilizando listas de palabras comunes.

#### Hallazgo relevante: `robots.txt`

Durante el escaneo se identificó el archivo **robots.txt**, el cual:
- No representa una vulnerabilidad directa
- Puede revelar rutas internas de interés
- Amplía la superficie de ataque desde un enfoque SOC

Este comportamiento es habitual en fases de **reconocimiento** y resulta especialmente didáctico en entornos intencionalmente vulnerables.

---

### 4️⃣ Análisis web (headers y protocolos)

Se analizaron respuestas HTTP/HTTPS para detectar:
- Uso de **HTTP sin cifrado**
- Redirecciones inseguras
- Exposición de versiones de servidor
- Configuración TLS

🔴 **Hallazgos comunes:**
- HTTP habilitado
- Login accesible sin cifrado
- TLS 1.0 / 1.1 habilitados
- Certificados no alineados con el dominio

------|--------------------|
| Información pública | Información contextual de amenazas |
| Datos de registro | Indicadores de compromiso |
| No indica riesgo | Evalúa reputación y actividad maliciosa |

---

### 3️⃣ Análisis web (headers y protocolos)

Se analizaron respuestas HTTP/HTTPS para detectar:
- Uso de **HTTP sin cifrado**
- Redirecciones inseguras
- Exposición de versiones de servidor
- Configuración TLS

🔴 **Hallazgos comunes:**
- HTTP habilitado
- Login accesible sin cifrado
- TLS 1.0 / 1.1 habilitados
- Certificados no alineados con el dominio

---

### 4️⃣ Enumeración de subdominios (entorno controlado)

La búsqueda de subdominios se realizó **exclusivamente sobre Metasploitable**, utilizando la **IP interna asignada por la máquina virtual**.

Objetivos:
- Ampliar la superficie de ataque
- Detectar servicios no documentados
- Practicar técnicas comunes de reconocimiento

---

## 📊 Resultados

### Riesgos identificados (nivel laboratorio)

- Configuraciones web inseguras
- Uso de protocolos obsoletos
- Falta de forzado de HTTPS
- Infraestructura sin capas de protección adicionales

⚠️ **No se detectaron ataques activos ni compromisos**.  
Los hallazgos corresponden a **riesgos de configuración**.

---

## 🧠 Enfoque SOC

Desde la perspectiva de un SOC Trainee:

- Estos hallazgos se **documentan**
- Se **escalan como riesgo**
- No se explotan
- Se proponen **recomendaciones de mitigación**

---

## ✅ Recomendaciones generales

- Forzar HTTPS
- Deshabilitar TLS legacy
- Usar certificados por dominio
- Ocultar versiones de servidor
- Implementar HSTS
- Mantener servicios actualizados

---

## 🔐 Anonimización y ética

- Dominios reales → **anonimizados**
- IPs públicas → **ocultas**
- Rutas sensibles → **generalizadas**
- Pruebas activas → **solo en laboratorio**

### Disclaimer
> Este proyecto fue realizado con fines **educativos**. No se realizaron pruebas ofensivas sobre sistemas productivos. El contenido fue anonimizado siguiendo buenas prácticas profesionales.

---

