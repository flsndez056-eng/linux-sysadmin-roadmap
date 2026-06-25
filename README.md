# 🐧 Linux SysAdmin & DevOps Roadmap

Repositorio dedicado a documentar mi progreso, laboratorios prácticos y resolución de problemas en entornos Linux, enfocado en adquirir habilidades de nivel producción.

## 📁 Estructura del Proyecto
*   **Módulo 1: Fundamentos y Navegación** (Semanas 1-3)
*   **Módulo 2: Administración y Permisos** (Próximamente)

---

## 🛠️ Módulo 1: Semana 1 - Acceso y Arquitectura
### Laboratorio Realizado: Configuración de Entorno WSL2
*   **Objetivo:** Levantar un entorno Linux Ubuntu nativo sobre Windows 10 y asegurar la conexión vía llaves SSH con GitHub.
*   **Comandos clave aprendidos:** `uname`, `hostname`, `man`, `cat`.
- [x] Tarea Semana 1: Entorno WSL2 y Banner .bashrc configurados.

## Modulo 1: Semana 2 - Navegacion Estructurada 
### Laboratorio Realizado: Inspeccionde Reconoicimiento a Ciegas
*   **Objetivo:** Navegar por la Terminal.
*   **Comandos clave aprendidos:** `ls` `cd` `pwd`. 
- [x] Tarea Semana 2: Investigacion de FHS y Navegacion Completada.

## Modulo 1: Semana 3 - Manipulacion de Entornos.
### Laboratorio Realizado: Creacion de carpetas anidadas.
*   **Objetivos:** Aprender a crear estructura completa de directorios.
*   **Comandos clave apredndidos:** `mkdir` `touch` `cp` `mv` `rm`
- [X] Tarea Semana 3: Preparar almacenamiento temporal para una app web completada.

---

## Proyecto Final Módulo 1: Simulación de Auditoría (Ticket #003)

*  **Objetivo:** Cumplir con un procedimiento operativo estándar (SOP) para centralizar, renombrar y auditar archivos de configuración críticos antes de una migración Cloud, aplicando navegación a ciegas y manipulación avanzada.

### Pasos Ejecutados y Solución Técnica:
1. **Creación de Entorno Protegido:** Se generó la estructura jerárquica ani     dada solicitada en un único comando optimizado:
   
     mkdir -p ~/auditoria_produccion/backups/nginx/configs/

2. **Extracción y Aislamiento de Datos:** Navegando al directorio raíz de co     nfiguraciones, se copió el archivo de red local sin afectar el entorno      operativo: 

     cp /etc/networks ~/auditoria_produccion/backups/nginx/configs/

3. **Estandarización de Nomenclatura:** Se renombró el activo para cumplir c     on las políticas de retención de la auditoría:
 
     cd ~/auditoria_produccion/backups/nginx/configs/
     mv networks networks.backup.old

4. **Reporte de Capacidad (Human-Readable):** Se exportó el metadato del pes     o del archivo directamente a un reporte técnico:

     ls -lh networks.backup.old > ~/auditoria_produccion/reporte_peso.txt4

5. **Auditoría de Trazabilidad del SysAdmin:** Se extrajeron los últimos 20      comandos del historial para auditoría forense interna:

     history | tail -n 20 > ~/comandos_auditorados.log





## Módulo 2: Administración y Permisos

### Semana 4 - Gestión de Identidades
* ** Objetivo:** Modificar privilegios y accesos concurrentes de la identidad dev_pedro para asignarlo a proyectos mutuos entre los departamentos de Ingeniería (devteam) y Datos (analytics) bajo el principio de menor privilegio.

## Pasos Ejecutados y Solución Técnica:

1. **Asignación Colectiva (Append):** Se utilizó el flag de anexado seguro (     -aG) para asegurar que el usuario mantenga sus accesos originales en de     vteam mientras se le otorgan permisos en el nuevo esquema:

     sudo usermod -aG analytics dev_pedro

2. **Auditoría de Identidad Basada en IDs:** Se validó que el sistema recono     zca al usuario con múltiples pertenencias de grupo concurrentes:

     id dev_pedro
     Output de verificación del sistema:
     uid=1001(dev_pedro) gid=1001(devteam) groups=1001(devteam),1002(analyti     cs)

3. **Verificación en Archivo de Configuración de Grupos:** Se auditó directa     mente la persistencia en la base de datos de identidades del sistema op     erativo empleando herramientas de filtrado de texto:

     tail -n 5 /etc/group | grep analytics
     Output de verificación del sistema:
     analytics:x:1002:dev_pedro
















