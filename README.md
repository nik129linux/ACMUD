# 🤖 Asistente Inteligente en WhatsApp para PYMEs (n8n + IA)

## 🧩 Descripción General
Este proyecto consiste en el desarrollo de un **asistente automatizado de ventas y atención al cliente** para pequeñas y medianas empresas (**PYMEs**).  
La solución está construida sobre **n8n**, integrando **Twilio** para la comunicación vía WhatsApp y **OpenAI** para el análisis e interpretación de mensajes.

El sistema funciona como un **bot de ventas 24/7**, capaz de:
- Atender consultas y solicitudes en lenguaje natural.  
- Consultar inventarios en tiempo real.  
- Registrar leads y generar recordatorios automáticos.  
- Enviar cotizaciones o respuestas personalizadas según el catálogo.  

Su propósito principal es **automatizar hasta el 90% de las interacciones rutinarias**, reduciendo costos y mejorando la eficiencia de atención al cliente en negocios locales.

---

## 💡 Motivación
En 2025, WhatsApp se mantiene como la **principal plataforma de comunicación comercial** en América Latina, con más de **2 mil millones de usuarios activos**.  
Las PYMEs, que dependen fuertemente de este canal, enfrentan limitaciones para ofrecer atención continua sin elevar costos operativos.

Este proyecto busca resolver ese desafío mediante:
- **Atención instantánea** y disponible 24/7.  
- **Gestión automatizada de leads** con seguimientos programados.  
- **Control de inventario y cotizaciones** en tiempo real.  
- **Respuestas personalizadas** según el tipo de negocio o sector.

> 🎯 Objetivo: aumentar la eficiencia operativa y la conversión de ventas a través de la automatización inteligente.

---

## ⚙️ Stack Tecnológico

| Componente | Tecnología | Descripción |
|-------------|-------------|--------------|
| **Plataforma principal** | [n8n v1.50+](https://n8n.io/) | Entorno low-code para crear workflows visuales y conectar APIs. |
| **Integración con WhatsApp** | [Twilio API](https://www.twilio.com/whatsapp) | Envía y recibe mensajes, permite pruebas con sandbox gratuito. |
| **Motor de IA** | [Google AI Studio API](https://aistudio.google.com) / AI Node | Analiza, clasifica y genera respuestas naturales en lenguaje humano. |
| **Gestión de datos** | SQLite / PostgreSQL / Google Sheets | Consulta y registro de interacciones, stock y leads. |
| **Automatización** | Cron / Scheduler Node | Crea recordatorios y seguimientos automáticos. |
| **Despliegue** | Docker / n8n Self-host / Heroku + Ngrok | Permite ejecución local o en la nube a bajo costo (<5 USD/mes). |

---

## 🧠 Arquitectura y Lógica del Agente

El sistema se organiza como un flujo modular dentro de **n8n**, donde cada nodo ejecuta una tarea específica de procesamiento o integración.  

### 🔄 Flujo General

1. **Recepción del mensaje (Twilio Trigger)**  
   Captura el texto y los datos del cliente.  
2. **Preprocesamiento (Function Node)**  
   Extrae campos relevantes (mensaje, usuario, producto).  
3. **Análisis con IA (OpenAI Node)**  
   Determina intención, nivel de interés y tipo de producto.  
4. **Ruteo lógico (Switch Node)**  
   Redirige el flujo a la acción adecuada (consulta, venta, seguimiento, FAQ).  
5. **Consulta de stock (SQL Node)**  
   Verifica disponibilidad y precios.  
6. **Generación de respuesta (AI Node)**  
   Produce un mensaje natural con datos actualizados y CTA.  
7. **Envío (Twilio Outbound)**  
   Envía texto o multimedia al usuario.  
8. **Registro (SQL Node)**  
   Guarda toda la interacción en la base de datos.  
9. **Seguimiento (Scheduler Node)**  
   Envía recordatorios automáticos a leads sin respuesta.

⏱ **Tiempo promedio por ciclo:** < 3 segundos  
🧩 **Manejo de errores:** rutas alternativas ante fallos de API o falta de stock.  

---

### 🗺 Diagrama de Flujo (Mermaid)
<img width="573" height="1600" alt="image" src="https://github.com/user-attachments/assets/d26012ae-3830-4914-94b4-6630921ec5c4" />

## 🧾 Conclusión

- El Asistente Inteligente en WhatsApp para PYMEs es una solución práctica, accesible y escalable que digitaliza la atención al cliente y optimiza las ventas mediante automatización e inteligencia artificial.
- Gracias a su arquitectura modular en n8n, puede adaptarse fácilmente a diferentes tipos de negocios, manteniendo bajo costo y alta eficiencia operativa.


