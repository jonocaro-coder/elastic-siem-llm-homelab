# elastic-siem-llm-homelab  
Laboratorio SIEM con Elastic Stack, telemetría multiplataforma y asistencia LLM para análisis de alertas.

# Descripción general  
Este proyecto es un laboratorio SIEM reproducible que integra:

Elastic Stack para la ingesta, normalización y análisis de telemetría.  
Endpoints Windows y Linux con VirtualBox, configurados con Sysmon, Winlogbeat y Elastic Agent.  
Un asistente LLM local (Ollama) diseñado mediante principios de context engineering para apoyar investigaciones SOC.

El laboratorio está orientado a mostrar competencias prácticas en arquitectura SIEM, detección de amenazas, análisis de eventos y uso de modelos de lenguaje como apoyo en tareas de investigación.

# Objetivos del proyecto

- Montar un SIEM reproducible con Elastic Stack y telemetría real de Windows y Linux.  
- Practicar análisis y detección apoyándose en dashboards y reglas basadas en MITRE ATT&CK.  
- Integrar un asistente LLM local para acelerar investigaciones y explicar comportamientos.  
- Aplicar principios de context engineering, definiendo qué información recibe el LLM y cómo debe trabajar con ella.

## Arquitectura del laboratorio

```
Arquitectura del laboratorio
│
├── Endpoints Windows
│   ├── Windows 10 VM
│   └── Windows Server VM (En proceso)
│
├── Endpoint Linux
│   └── Ubuntu Server VM (En proceso)
│
├── Elastic Stack (Docker)
│   ├── Elasticsearch
│   └── Kibana
│
└── Asistente LLM
    ├── Ollama Server
    └── Prompts + Context Engineering
```

# Descripción de componentes

Windows 10 VM
Telemetría detallada mediante Sysmon y Winlogbeat para análisis de procesos, red y eventos de seguridad.

Windows Server VM (En proceso)  
Segundo endpoint Windows para simular entornos corporativos y validar detecciones en múltiples hosts.

Ubuntu Server VM (En proceso) 
Logs de autenticación, procesos y actividad del sistema mediante Elastic Agent o Syslog.

Elasticsearch
Motor central del SIEM: almacenamiento, indexación y consulta de toda la telemetría.

Kibana
Interfaz de análisis: dashboards, reglas de detección, consultas y vistas de investigación.

Ollama Server
Modelo LLM local para análisis de alertas, resúmenes y explicación de comportamientos.

Prompts y Context Engineering  
Plantillas y reglas que definen qué información recibe el LLM y cómo debe procesarla dentro del flujo SOC.

## Características principales

- Elastic Stack desplegado con Docker, pensado para un entorno reproducible y fácil de levantar.  
- Telemetría real desde Windows y Linux, utilizando Sysmon, Winlogbeat y Elastic Agent según la plataforma.  
- Dashboards de Kibana (planificados) centrados en procesos, autenticaciones, actividad de red y vistas de investigación.  
- Detecciones basadas en MITRE ATT&CK (planificadas), organizadas por plataforma y orientadas a escenarios prácticos.  
- Asistente LLM local (Ollama) para apoyar el análisis de alertas, generar resúmenes y explicar reglas o comportamientos.  
- Context engineering aplicado al SOC, definiendo qué información recibe el LLM, cómo se estructura y qué límites tiene dentro del flujo de investigación.  
- Scripts de automatización del laboratorio (planificados).

## Estructura del repositorio

```
elastic-siem-llm-homelab/
├─ README.md
├─ .gitignore
│
├─ architecture/
│  ├─ architecture-diagram.png
│  └─ architecture.md
│
├─ docs/
│  └─ use-cases.md
│
├─ lab-setup/
│  └─ host/
│     └─ elastic-config/
│        ├─ elasticsearch.yml
│        ├─ kibana.yml
│        ├─ logstash.yml
│        ├─ pipeline.conf
│        ├─ docker-compose.yml
│        └─ env.example
│
├─ telemetry/
│  ├─ elastic-agent-config.yml
│  ├─ sysmon-config.yml
│  └─ winlogbeat-config.yml
│
├─ llm/
│  ├─ ollama-setup.md
│  └─ prompt-examples.md
│  # workflow.md (En proceso)
│  # context-engineering.md (En proceso)
│
├─ detections/ (planificado)
│  ├─ windows/
│  ├─ linux/
│  └─ kibana-export.ndjson
│
├─ dashboards/ (En proceso)
│  ├─ windows-overview.ndjson
│  ├─ linux-overview.ndjson
│  └─ investigation-views.ndjson
│
└─ notes/ (planificado)
   ├─ troubleshooting.md
   └─ roadmap.md
```

## Requisitos previos

- Windows 11, Ubuntu o WSL2  
- Docker Desktop / Docker Engine  
- 16 GB RAM recomendados  
- Sysmon instalado en endpoints Windows  
- PowerShell (para scripts en Windows)

## Estado del proyecto

### Completado
- Arquitectura inicial del laboratorio definida y documentada (`architecture/`).  
- Elastic Stack desplegado en Docker con configuración propia (`lab-setup/host/elastic-config/`).  
- Telemetría real desde Windows 10 integrada (Sysmon + Winlogbeat).  

### En proceso
- Creación y afinado de reglas de detección en Kibana (exportables a `detections/`).  
- Desarrollo de dashboards iniciales para Windows y vistas de investigación (`dashboards/`).
- Base del módulo LLM creada: configuración de Ollama y prompts iniciales (`llm/`).
- Profundización en context engineering para el asistente LLM (`llm/`).  
- Preparación de máquinas virtuales Windows Server y Ubuntu para extender la telemetría.

### Pendiente
- Integración de Elastic Agent en Ubuntu Server.  
- Integración de telemetría desde Windows Server.  
- Casos de uso basados en MITRE ATT&CK (`docs/use-cases.md`).  
- Automatización avanzada del laboratorio (scripts de orquestación y análisis asistido por IA).  
- Documentación adicional (`docs/project-status.md`, `docs/notes.md`, `notes/`).

## Documentación

La documentación conceptual y técnica se encuentra en:

- **/architecture** — Arquitectura y diagramas del laboratorio.  
- **/docs** — Casos de uso y documentación futura del proyecto.  
- **/llm** — Configuración de Ollama y prompts iniciales; incluirá flujo de trabajo y diseño de contexto.  
- **/telemetry** — Configuración de telemetría para Windows y Linux.  
- **/notes** *(planificado)* — Troubleshooting y roadmap del proyecto.

## Contribuciones

El proyecto está abierto a sugerencias y mejoras.  
Cualquier aportación será revisada y considerada.

## Licencia

MIT License *(En proceso)*.

    

    
