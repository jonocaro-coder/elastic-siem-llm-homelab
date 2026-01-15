# elastic-siem-llm-homelab
Laboratorio SIEM con Elastic Stack, telemetría multiplataforma y asistencia LLM para análisis de alertas.

# Descripción general
Este proyecto es un laboratorio SIEM reproducible que integra:
- Elastic Stack para la ingesta, normalización y análisis de telemetría.
- Endpoints Windows y Linux reales, configurados con Sysmon, Winlogbeat y Elastic Agent.
- Un asistente LLM local (Ollama) diseñado mediante principios de context engineering para apoyar investigaciones SOC.
El laboratorio está orientado a mostrar competencias prácticas en arquitectura SIEM, detección de amenazas, análisis de eventos y uso de modelos de lenguaje como apoyo en tareas de investigación.

# Objetivos del proyecto
- Montar un SIEM reproducible con Elastic Stack y telemetría real de Windows y Linux.
- Practicar análisis y detección, apoyándose en dashboards y reglas basadas en MITRE ATT&CK.
- Integrar un asistente LLM local para acelerar investigaciones y explicar comportamientos.
- Aplicar principios de context engineering, definiendo qué información recibe el LLM y cómo debe trabajar con ella.

# Arquitectura del laboratorio
```
Arquitectura del laboratorio
│
├── Endpoints Windows
│   ├── Windows 10 VM
│   └── Windows Server VM
│
├── Endpoint Linux
│   └── Ubuntu Server VM
│
├── Elastic Stack (Docker)
│   ├── Elasticsearch
│   └── Kibana
│
└── Asistente LLM
    ├── Ollama Server
    └── Prompts + Context Engineering
````
· Descripción de componentes

Windows 10 VM
Telemetría detallada mediante Sysmon y Winlogbeat para análisis de procesos, red y eventos de seguridad.

Windows Server VM
Segundo endpoint Windows para simular entornos corporativos y validar detecciones en múltiples hosts.

Ubuntu Server VM
Logs de autenticación, procesos y actividad del sistema mediante Elastic Agent o Syslog.

Elasticsearch
Motor central del SIEM: almacenamiento, indexación y consulta de toda la telemetría.

Kibana
Interfaz de análisis: dashboards, reglas de detección, consultas y vistas de investigación.

Ollama Server
Modelo LLM local para análisis de alertas, resúmenes y explicación de comportamientos.

Prompts + Context Engineering
Plantillas y reglas que definen qué información recibe el LLM y cómo debe procesarla dentro del flujo SOC

# Características principales
- Elastic Stack desplegado con Docker, pensado para un entorno reproducible y fácil de levantar.
- Telemetría real desde Windows y Linux, utilizando Sysmon, Winlogbeat y Elastic Agent según la plataforma.
- Dashboards de Kibana listos para usar, centrados en procesos, autenticaciones, actividad de red y vistas de investigación.
- Detecciones basadas en MITRE ATT&CK, organizadas por plataforma y orientadas a escenarios prácticos.
- Asistente LLM local (Ollama) para apoyar el análisis de alertas, generar resúmenes y explicar reglas o comportamientos.
- Context engineering aplicado al SOC, definiendo qué información recibe el LLM, cómo se estructura y qué límites tiene dentro del flujo de investigación.
- Scripts de automatización para iniciar y detener el laboratorio sin necesidad de ejecutar comandos manuales.

# Estructura del repositorio
````
elastic-siem-llm-homelab/
├─ README.md
├─ LICENSE
├─ .gitignore
├─ docs/
│  ├─ architecture-diagram.drawio
│  ├─ architecture-diagram.png
│  ├─ architecture-mermaid.md
│  └─ use-cases.md
├─ lab-setup/
│  ├─ host/
│  │  ├─ docker-compose.yml
│  │  └─ elastic-config/
│  ├─ vms/
│  │  ├─ windows-10/
│  │  │  ├─ sysmon-config.xml
│  │  │  └─ winlogbeat.yml
│  │  ├─ windows-server/
│  │  │  ├─ sysmon-config.xml
│  │  │  └─ winlogbeat.yml
│  │  └─ ubuntu-server/
│  │     └─ elastic-agent-notes.md
│  └─ scripts/
│     ├─ start-lab.ps1
│     ├─ stop-lab.ps1
│     └─ helpers/
├─ detections/
│  ├─ windows/
│  │  ├─ process_creation/
│  │  └─ lateral_movement/
│  ├─ linux/
│  │  └─ ssh_sudo/
│  └─ kibana-export.ndjson
├─ dashboards/
│  ├─ windows-overview.ndjson
│  ├─ linux-overview.ndjson
│  └─ investigation-views.ndjson
├─ llm-assistant/
│  ├─ prompts/
│  │  ├─ alert-summary.md
│  │  ├─ rule-explanation.md
│  │  └─ investigation-support.md
│  ├─ workflow.md
│  └─ context-engineering.md
└─ notes/
   ├─ troubleshooting.md
   └─ roadmap.md
````
# Requisitos previos
- Windows 11, Ubuntu o WSL2
- Docker Desktop / Docker Engine
- 16 GB RAM recomendados
- Sysmon instalado en endpoints Windows
- PowerShell (para scripts en Windows)

# Estado del proyecto
El laboratorio está actualmente en desarrollo.
Las instrucciones completas de despliegue se publicarán cuando todos los componentes estén integrados y verificados.

# Documentación

# Contribuciones


# Licencia









    

    
