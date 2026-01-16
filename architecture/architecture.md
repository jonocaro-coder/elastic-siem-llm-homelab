# Arquitectura del Laboratorio SIEM + LLM

Este laboratorio combina Elastic Stack, telemetría multiplataforma y un modelo LLM local para apoyar tareas de análisis, resumen y explicación de alertas.

# Componentes principales

- **Elastic Stack (Docker)**
  - Elasticsearch
  - Kibana

- **Telemetría**
  - Windows 10: Sysmon + Winlogbeat
  - Windows Server: Sysmon + Winlogbeat
  - Ubuntu Server: Elastic Agent

- **LLM (Ollama)**
  - Resumen de alertas
  - Explicación de reglas
  - Apoyo en investigaciones

Consulta el diagrama incluido en este directorio para una visión visual del flujo de datos.
