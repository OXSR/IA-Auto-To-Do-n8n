# IA auto To-Do (n8n + GPT + ClickUp)

Este workflow de **n8n** automatiza la creación de tareas en **ClickUp** a partir de correos electrónicos, usando **OpenAI (GPT)** para interpretar y reorganizar el contenido.

## ¿Cómo funciona?

1. **Trigger de Email (Gmail/IMAP):**  
   Escucha nuevos correos entrantes.

2. **Filtrado de remitentes:**  
   Solo procesa mensajes de usuarios autorizados.

3. **Procesamiento con IA:**  
   Envía el asunto y contenido del correo a **GPT-4o-mini**, que:
   - Genera una lista de tareas.
   - Asigna una prioridad (1–3).
   - Estima el tiempo requerido.

4. **Parsing del JSON:**  
   Extrae y limpia los datos de la respuesta del modelo y reordena el JSON (se hizo así para evitar altos costes en OpenAI).

5. **Creación de la tarea en ClickUp:**  
   La tarea se crea automáticamente con:
   - Título = Asunto del correo  
   - Contenido = Lista de tareas + tiempo estimado  
   - Prioridad y estado  
   - Notificación a todo el equipo
   - Etiqueta

## Tecnologías usadas

- [n8n](https://n8n.io/)
- [OpenAI API](https://platform.openai.com/)
- [ClickUp API](https://clickup.com/api)

## Requisitos

- Cuenta en **n8n** (cloud o self-hosted)  
- Conexión configurada a:
  - Gmail o servidor IMAP  
  - OpenAI  
  - ClickUp  

## 📎 Nota

El flujo está diseñado para ser modular y fácilmente adaptable a otras herramientas como Notion, Trello o Asana.

---

