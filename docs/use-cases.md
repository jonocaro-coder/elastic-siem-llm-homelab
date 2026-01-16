# Casos de Uso del Laboratorio SIEM + LLM

Este laboratorio combina Elastic Stack, telemetría multiplataforma y un modelo LLM local para apoyar tareas de detección, análisis y respuesta. Los siguientes casos de uso representan escenarios reales que un analista SOC podría investigar utilizando este entorno.

---

## 1. Ejecución sospechosa en Windows (Sysmon + Winlogbeat)

**Descripción**  
Un proceso inusual se ejecuta en un endpoint Windows 10 o Windows Server. Sysmon registra la creación del proceso y Winlogbeat envía el evento a Elasticsearch.

**Objetivo**  
Detectar actividad potencialmente maliciosa basada en patrones de ejecución, rutas anómalas o herencia de procesos.

**Flujo**  
1. Sysmon genera un evento `ProcessCreate (Event ID 1)`.  
2. Winlogbeat lo envía a Elasticsearch.  
3. Kibana lo visualiza en dashboards o alertas.  
4. El analista puede enviar el evento al LLM para obtener:  
   - Resumen en lenguaje natural  
   - Explicación del riesgo  
   - Posibles técnicas MITRE ATT&CK relacionadas  

**Valor añadido del LLM**  
Acelera la interpretación del evento y reduce el tiempo de análisis.

---

## 2. Acceso sospechoso vía SSH en Ubuntu (Elastic Agent)

**Descripción**  
Un atacante intenta autenticarse en el servidor Ubuntu mediante SSH, con múltiples intentos fallidos o desde una IP inusual.

**Objetivo**  
Detectar actividad de fuerza bruta o accesos no autorizados.

**Flujo**  
1. Elastic Agent recoge eventos de `auth.log`.  
2. Los envía a Elasticsearch.  
3. Kibana genera una alerta basada en umbrales o patrones.  
4. El LLM puede:  
   - Resumir la alerta  
   - Explicar el patrón de ataque  
   - Sugerir pasos de investigación  

**Valor añadido del LLM**  
Permite contextualizar rápidamente si el intento es benigno o malicioso.

---

## 3. Actividad administrativa anómala en Windows Server

**Descripción**  
Un usuario realiza acciones administrativas inesperadas:  
- Creación de cuentas  
- Cambios en servicios  
- Elevación de privilegios  

**Objetivo**  
Detectar abuso de privilegios o movimientos laterales.

**Flujo**  
1. Sysmon y Winlogbeat capturan eventos de administración.  
2. Elasticsearch almacena y correlaciona los datos.  
3. Kibana muestra patrones de actividad.  
4. El LLM ayuda a:  
   - Explicar el impacto de la acción  
   - Identificar si coincide con técnicas MITRE como T1078 o T1053  
   - Proponer hipótesis de investigación  

**Valor añadido del LLM**  
Traduce eventos técnicos en explicaciones claras y accionables.

---

## 4. Resumen automático de alertas en Kibana mediante LLM

**Descripción**  
El analista copia una alerta compleja de Kibana y la envía al LLM para obtener un resumen claro y contextualizado.

**Objetivo**  
Reducir la carga cognitiva y acelerar la toma de decisiones.

**Flujo**  
1. Kibana genera una alerta basada en reglas.  
2. El analista copia el JSON o mensaje.  
3. El LLM produce:  
   - Resumen  
   - Riesgo potencial  
   - Técnicas MITRE  
   - Recomendaciones  

**Valor añadido del LLM**  
Transforma datos crudos en información útil para el analista.

---

## 5. Correlación básica entre hosts (Windows + Ubuntu)

**Descripción**  
Eventos dispersos en distintos sistemas pueden estar relacionados:  
- Un proceso sospechoso en Windows  
- Un intento de SSH desde la misma IP  
- Un cambio de servicio en Windows Server  

**Objetivo**  
Identificar patrones que indiquen un ataque coordinado.

**Flujo**  
1. Elasticsearch recibe telemetría de múltiples fuentes.  
2. Kibana permite correlacionar por IP, usuario o timestamp.  
3. El LLM ayuda a:  
   - Explicar la posible relación entre eventos  
   - Proponer hipótesis de ataque  
   - Identificar técnicas MITRE asociadas  

**Valor añadido del LLM**  
Facilita la correlación conceptual entre eventos heterogéneos.

---

## 6. Explicación de reglas de detección (Detections Engine)

**Descripción**  
El analista quiere entender qué hace una regla de detección de Elastic.

**Objetivo**  
Aumentar la comprensión del motor de detecciones y mejorar la capacidad de tuning.

**Flujo**  
1. El analista copia la regla en formato YAML o JSON.  
2. El LLM explica:  
   - Qué detecta  
   - Qué campos usa  
   - Qué comportamiento malicioso cubre  
   - Limitaciones o falsos positivos comunes  

**Valor añadido del LLM**  
Permite aprender y ajustar reglas más rápido.

---

# Conclusión

Estos casos de uso muestran cómo el laboratorio combina telemetría real, Elastic Stack y un modelo LLM local para crear un entorno didáctico y práctico orientado a detección, análisis y respuesta. El objetivo es simular el trabajo de un analista SOC moderno, apoyado por IA para acelerar la investigación y mejorar la comprensión de los eventos.
