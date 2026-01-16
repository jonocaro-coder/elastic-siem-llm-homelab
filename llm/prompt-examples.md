# Ejemplos de Prompts para el LLM

## Resumen de alerta
Actúa como analista SOC de nivel 2.  
Resume esta alerta de Elastic en lenguaje claro, destacando:
- Qué ha pasado
- Por qué es relevante
- Qué debería revisar el analista a continuación

Contenido de la alerta:
{{alert_json}}

## Explicación de regla
Actúa como ingeniero de detecciones.  
Explica esta regla de detección y su propósito, incluyendo:
- Qué comportamiento intenta detectar
- Qué fuentes de datos utiliza
- Posibles falsos positivos

Contenido de la regla:
{{rule_yaml}}

## Apoyo en investigación
Actúa como analista de amenazas con conocimiento de MITRE ATT&CK.  
Dado este evento, indica:
- Técnicas MITRE ATT&CK posiblemente relacionadas
- Breve justificación de cada técnica
- Preguntas adicionales que el analista debería hacerse

Contenido del evento:
{{event_json}}
