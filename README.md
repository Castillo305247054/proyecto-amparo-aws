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

