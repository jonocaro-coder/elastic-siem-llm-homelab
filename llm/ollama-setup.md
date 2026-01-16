# Configuración de Ollama para el Laboratorio SIEM + LLM

## Instalación
1. Descargar Ollama desde https://ollama.ai
2. Instalar un modelo base:
   ollama pull llama2
3. Verificar que Ollama funciona correctamente:
   ollama run llama2

## Requisitos
- Sistema operativo compatible (Windows, macOS o Linux)
- Al menos 8 GB de RAM recomendados
- Conexión a Internet para descargar modelos

## Integración con Elastic
El modelo LLM se utilizará para:
- Resumir alertas de Elastic
- Explicar reglas de detección
- Apoyar investigaciones SOC
- Relacionar eventos con técnicas MITRE ATT&CK

La integración se realizará mediante scripts que:
1. Consultan Elasticsearch
2. Extraen eventos, reglas o alertas
3. Envían el contenido al modelo LLM para su análisis
4. Devuelven un resumen o explicación contextual

## Estado
Este módulo está en desarrollo (WIP) y se integrará con:
- `llm/prompt-examples.md`
- Scripts de automatización en `scripts/`
