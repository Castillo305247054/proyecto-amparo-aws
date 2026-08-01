# ⚖️ Generador Automático de Amparos Indirectos (AWS + GitHub Pages)

> **Solución de LegalOps & Serverless Cloud Architecture**  
> Automatización de redacción y captura de escritos de Amparo Indirecto, reduciendo el tiempo de procesamiento operativo de **45 minutos a menos de 1 segundo**, manteniendo una infraestructura con **costo $0 USD/mes**.

---

## 📌 Descripción del Proyecto

En la práctica jurídica tradicional, la captura manual de datos y la redacción de demandas consumen tiempo operativo valioso y aumentan el margen de error humano. 

Este proyecto implementa una **arquitectura Serverless en Amazon Web Services (AWS)** integrada con un frontend web en **GitHub Pages**. Permite a abogados de campo o clientes capturar información clave (*Quejoso, Autoridad Responsable, Acto Reclamado, Juzgado*) y generar automáticamente el borrador legal, registrar la bitácora en una base de datos NoSQL y notificar vía correo electrónico en tiempo real.

---

## 🏗️ Arquitectura del Sistema

```text
[ Formulario Web ] (GitHub Pages / HTML5 + JS)
        │
        ▼  (HTTPS POST / JSON)
[ Amazon API Gateway ]
        │
        ▼  (Invocación Asíncrona)
[ AWS Lambda ] (Python 3.12) ──► Genera la plantilla de Amparo
        │
        ├──► [ Amazon DynamoDB ] ──► Resguardo de expediente (NoSQL)
        │
        └──► [ Amazon SNS ] ──────► Alerta y borrador enviado por email



🛠️ Tecnologías Utilizadas
Frontend: HTML5, CSS3, JavaScript (Fetch API) alojado en GitHub Pages.


Backend / Compute: AWS Lambda (Python 3.12).
API Management: AWS API Gateway (REST API / CORS activado).
Database: Amazon DynamoDB (Base de datos NoSQL).
Notifications: Amazon Simple Notification Service (SNS).


🚀 Flujo de Trabajo (Step-by-Step)

Ingreso de Datos: El usuario llena el formulario web con los datos procesales.
Ingesta de Datos: Se envía un objeto JSON de forma segura mediante un endpoint HTTPS en API Gateway.
Procesamiento e Inserción: AWS Lambda ejecuta el script en Python, formatea las variables dentro de la estructura jurídica del Amparo Indirecto y almacena el registro en DynamoDB.
Notificación: Amazon SNS distribuye el borrador generado al correo electrónico configurado para revisión inmediata.


📂 Estructura del Repositorio

proyecto-amparo-aws/
│
├── index.html           # Interfaz de usuario (Frontend)
├── lambda_function.py   # Lógica en Python para AWS Lambda (Backend)
├── README.md            # Documentación del proyecto
└── .gitignore           # Archivos ignorados por Git


👤 Autor
Marco Antonio Castillo Frías

LegalOps | Business Intelligence | Data Analysis | Cloud Solutions

🌐 LinkedIn: linkedin.com/in/marco-antonio-castillo-frias
💻 GitHub: @Castillo305247054


Licencia MIT - Proyecto creado con fines educativos y de portafolio profesional.
