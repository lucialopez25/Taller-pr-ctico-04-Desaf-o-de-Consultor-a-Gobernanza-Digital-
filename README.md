# 

# 

# 

# 

# 

# AEE. Bitácora III. Conexiones Empresariales Taller Técnico: Operación Escudo 

Nombre y apellidos: Alba Durán Bernal  
Módulo: Sistemas Informáticos  
Fecha de entrega: 17/04/2026  
Docente: Willman Acosta Lugo 

# INDICE 

[**Fase de Investigación	3**](#fase-de-investigación)

[Reto de Investigación 1	3](#reto-de-investigación-1)

# **Fase de Investigación** {#fase-de-investigación}

## Reto de Investigación 1 {#reto-de-investigación-1}

*–Anatomía de Syslog–*  
Es el mecanismo que utiliza Linux para gestionar mensajes de registro de forma estructurada. Su función es almacenar eventos o mensajes de registro localmente dentro del dispositivo elegido y enviar esta información a un servidor Syslog para obtener, ordenar y filtrar todos los registros y datos que contiene.   
Para que un administrador pueda filtrar miles de eventos, Syslog clasifica cada mensaje mediante dos sectores: 

\-Facility: Identifica el subsistema o la categoría del software que genere el mensaje

* **0-7:** Mensajes de kernel, nivel de usuario, sistema de correo, demonios del sistema, seguridad/autorización.  
* **8-15:** Mensajes de usuarios, reloj, ftp, ntp, auditoría, alertas.  
* **16-23:** Usos locales (local0-local7), comúnmente utilizados para configuraciones personalizadas.

\-Severity: Define la importancia del evento en una escala del 0 al 7 

| Nivel  | Nombre (Inglés) | Descripción |
| :---- | :---- | :---- |
| **0** | **Emergency** | Sistema inutilizable (fallo catastrófico). |
| **1** | **Alert** | Acción inmediata necesaria (fallo crítico de componentes). |
| **2** | **Critical** | Condiciones críticas (fallo de hardware/software). |
| **3** | **Error** | Condiciones de error (operación fallida). |
| **4** | **Warning** | Condiciones de advertencia (algo inusual ocurrió). |
| **5** | **Notice** | Evento normal pero significativo. |
| **6** | **Informational** | Mensajes informativos (funcionamiento normal). |
| **7** | **Debug** | Mensajes de depuración (alto volumen). |

**¿Por qué es una negligencia grave que el archivo */var/log/auth.log* tenga permisos de lectura para usuarios no privilegiados?**

Que el archivo /var/log/auth.log sea legible por usuarios no privilegiados es una negligencia grave porque da a ver información importante y vulnerable acerca de la seguridad del sistema,  facilitando así la escalada de privilegios y el reconocimiento de los atacantes . Contiene un historial de intentos de inicio de sesión, uso de sudo, actividades de usuario**…**

**¿Qué información específica (como PIDs, nombres de usuario o direcciones IP) diferencia un intento fallido de conexión remota *SSH* de un simple fallo de contraseña de un usuario local frente a la pantalla?**

SSH: Ahí vemos un proceso de ssh cada conexión que vemos genera un PID, el cual es un número único que el sistema operativo le asigna a cada programa en el momento en el que este se empieza a ejecutar. En resumen, si vemos este nombre en el log es que alguien usó el internet para intentar entrar. 

Mientras que si es local, es decir, físico el responsable suele ser login o gdm. Si ves esto, es que alguien está tocando el teclado físico del ordenador, al contrario que el SHH no es algo remoto. 

## Reto de Investigación 2

* Cumplimiento y Log Management. Busca en **Dialnet** o **Semantic Scholar** artículos sobre *Log Management* (Gestión centralizada de registros). A nivel empresarial y legal (piensa en el RGPD en España), ¿qué ventajas vitales ofrece enviar y custodiar los logs en un servidor externo seguro en lugar de mantenerlos dispersos e indefensos en la propia máquina que podría ser vulnerada?

### 1\. Protección contra la "Eliminación de Huellas"

Cuando un atacante logra comprometer un servidor, su primera prioridad es obtener privilegios de administrador para borrar los archivos de registro (/var/log).

\-En local: Si el atacante borra los logs en la máquina, la evidencia desaparece para siempre. No sabrás ni cómo entró ni qué se llevó.

\-En externo: Como los logs se envían en tiempo real (vía Syslog, por ejemplo), para cuando el atacante intenta borrarlos, la información ya ha sido copiada en el servidor externo.

2\. Cumplimiento Legal y RGPD (España)

El Reglamento General de Protección de Datos (RGPD) y la LOPDGDD en España exigen que las organizaciones garanticen la integridad y la trazabilidad de los datos.

Centralizar los logs permite asegurar que no han sido manipulados. Esto crea una cadena que tiene validez legal ante una inspección de la AEPD (Agencia Española de Protección de Datos) o un juicio.

### 3\. Correlación de Eventos y Visibilidad Total

Un ataque rara vez afecta a una sola máquina; suele ser un movimiento lateral por toda la red. Al tener todos los registros en un solo lugar, puedes ver patrones que serían invisibles por separado. Por ejemplo: ver que una misma dirección IP falló en el SSH del Servidor A y, segundos después, logró entrar en la Base de Datos B.

Si un servidor es destruido o queda inaccesible debido a un ataque, los registros guardados externamente permiten reconstruir lo sucedido sin necesidad de recuperar el hardware dañado.

*–Bibliografía–*

\[1\] InvGate, "¿Qué es Syslog? Definición, funcionamiento y beneficios," *InvGate Blog*, 2024\. \[En línea\]. Disponible en: [https://blog.invgate.com/es/que-es-syslog](https://blog.invgate.com/es/que-es-syslog)

.\[2\] Pandora FMS, "¿Qué es Syslog? Una introducción al protocolo de registro del sistema," *Pandora FMS IT Topics*, 2024\. \[En línea\]. Disponible en: [https://pandorafms.com/es/it-topics/que-es-syslog-una-introduccion-al-protocolo-de-registro-del-sistema/](https://pandorafms.com/es/it-topics/que-es-syslog-una-introduccion-al-protocolo-de-registro-del-sistema/).

 \[3\] B. Das, "Why I Monitor /var/log/secure and Why Most Admins Don’t," *Medium*, 2021\. \[En línea\]. Disponible en: [https://medium.com/@bornaly/why-i-monitor-var-log-secure-and-why-most-admins-dont-3a362b1ad415](https://medium.com/@bornaly/why-i-monitor-var-log-secure-and-why-most-admins-dont-3a362b1ad415).

\[4\] Google, "Gemini (Versión de modelo Large Language Model)," *Google AI*, 2024\. \[En línea\]. Disponible en: [https://gemini.google.com](https://gemini.google.com). 

# 

