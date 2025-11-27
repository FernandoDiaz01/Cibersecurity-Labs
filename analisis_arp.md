Escaneo y documentación de red local (Home Network Assessment)

## Captura y análisis de tráfico ARP en entorno controlado

### 1. Identificación de la interfaz de red

Para iniciar el análisis, se verificó la interfaz de red activa en el
sistema Kali Linux mediante el comando:

    ifconfig

El resultado indicó que la interfaz utilizada para las comunicaciones de
red era **eth0**, configurada bajo un entorno virtualizado. Este paso
permitió determinar correctamente el punto de captura para el análisis
de tráfico.

### 2. Captura de tráfico ARP

Una vez identificada la interfaz, se procedió a iniciar la captura de
paquetes ARP utilizando la herramienta tcpdump:

    sudo tcpdump -i eth0 arp

El uso de permisos elevados es requerido debido a que la captura de
paquetes en modo promiscuo necesita privilegios administrativos. La
herramienta comenzó a escuchar tráfico ARP en la red local, mostrando
solicitudes y respuestas generadas por distintos dispositivos del
entorno controlado.

Para asegurar la aparición de paquetes ARP y facilitar su análisis, se
generó navegación web desde otro dispositivo dentro de la misma red.
Esto provocó resoluciones ARP naturales, ya que los equipos necesitan
traducir direcciones IP a direcciones MAC para establecer comunicación.

### 4. Resultados de la captura (con datos anonimizados)

**Nota:** Todas las direcciones IP y MAC fueron reemplazadas por valores
ficticios manteniendo el mismo formato y estructura que la captura
original. Esto garantiza privacidad sin perder el contexto técnico.

Durante la captura con tcpdump se observaron múltiples solicitudes y
respuestas ARP propias del funcionamiento normal de la red local. Estos
son ejemplos anonimizados del tráfico registrado:

    ARP Request: Who-has 192.168.10.1? Tell 192.168.10.20
    ARP Reply: 192.168.10.1 is-at AA:BB:CC:11:22:33

    ARP Request: Who-has 192.168.10.20? Tell 192.168.10.1
    ARP Reply: 192.168.10.20 is-at AA:BB:CC:44:55:66

En estos paquetes se observa: - Solicitudes ARP enviadas por distintos
dispositivos (PC, router, etc.) - Respuestas ARP devolviendo la
dirección MAC correspondiente - Comunicación habitual entre dispositivos
que necesitan resolver IP → MAC dentro de la red LAN

### 5. Interpretación del tráfico ARP capturado

Todo el tráfico observado corresponde a comportamiento normal y esperado
dentro de una red local:

-   **Solicitudes ARP (ARP Request):** Un dispositivo pregunta "¿quién
    tiene esta IP?" para conocer la dirección MAC de otro equipo.\
-   **Respuestas ARP (ARP Reply):** El equipo que posee la IP responde
    con su dirección MAC, permitiendo la comunicación.

No se detectaron anomalías, respuestas duplicadas ni indicios de ARP
spoofing durante esta captura inicial.

### 6. Conclusión

La captura realizada permitió: - Comprobar que la red está resolviendo
direcciones IP ↔ MAC correctamente. - Visualizar cómo los dispositivos
interactúan con el router mediante ARP. - Verificar que no existen
comportamientos sospechosos en el tráfico analizado.

Este ejercicio constituye un paso fundamental para desarrollar
habilidades de análisis de tráfico en entornos seguros antes de avanzar
hacia técnicas ofensivas controladas.