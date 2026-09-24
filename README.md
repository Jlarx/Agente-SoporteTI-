# 🤖 SupportAi: Agente Inteligente de Soporte TI

![Banner](https://img.shields.io/badge/Status-Activo-success?style=for-the-badge) ![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python) ![Groq](https://img.shields.io/badge/LLM-Groq-orange?style=for-the-badge) ![FAISS](https://img.shields.io/badge/Motor_de_Búsqueda-FAISS-red?style=for-the-badge)

## 📌 Contexto del Proyecto

**SupportAi** nace con el objetivo de resolver un cuello de botella muy común en el mundo real: **la saturación de las mesas de ayuda de TI**.

Inspirado en la operación de sistemas de tickets reales como *Jira Service Desk*, este proyecto busca aliviar al equipo de soporte de Nivel 1, que frecuentemente invierte más del 50% de su tiempo respondiendo manualmente las mismas preguntas repetitivas:

1. 🔑 ¿Cómo cambio mi contraseña?
2. 📧 ¿Cómo configuro el correo institucional?
3. 🔒 ¿Qué hago si se bloqueó mi cuenta?
4. 📱 ¿Cómo solicito acceso a una aplicación?
5. 🛜 ¿Cómo conecto el computador al Wi-Fi?
6. 📝 ¿Cuál es el procedimiento para reportar un problema?

## 🚀 El Problema y Nuestra Solución

Implementar un LLM tradicional directamente representaba un riesgo, ya que la IA podría **alucinar** y entregar a los usuarios instrucciones que no corresponden a las reglas de la compañía (ej: sugerir contraseñas cortas cuando las políticas exigen 12 caracteres).

Para solucionar esto de manera segura, diseñamos una arquitectura **RAG (Retrieval-Augmented Generation)**:

1. **Recuperación (Retrieval):** Cuando el usuario hace una pregunta, buscamos en nuestra base de datos (usando **FAISS**) el manual o artículo que resuelve esa duda específica.
2. **Generación:** Le pasamos esa documentación oficial al modelo LLM (**Groq**) para que redacte una respuesta amigable basándose **únicamente** en los lineamientos de la empresa.

## 🛠️ Tecnologías y Arquitectura

* **Motor de Búsqueda Vectorial:** `FAISS` para la similitud y recuperación de documentos.
* **Modelo LLM:** `Groq` para una generación rápida y eficiente.
* **Embeddings:** `sentence-transformers` para convertir los textos y consultas en vectores.
* **Análisis de Datos:** `Pandas`, `Numpy` y `Matplotlib`.

### ¿Por qué FAISS?
Cuando un empleado realiza una consulta, el sistema convierte su pregunta en un vector y lo compara matemáticamente con los vectores de nuestros manuales, identificando exactamente qué contenido es el más relevante.

## 📂 Estructura del Repositorio

* **`Agente-TI.ipynb` (Código Fuente):** Notebook principal con todo el código, flujo metodológico y configuración del modelo.
* **`Diagrama.png` (Diagrama):** Diagrama de la arquitectura de la solución RAG.
* **`Evaluacion1-IA.pdf` (Informe):** Documento con el informe técnico del proyecto.
* **`README.md` (Información del Proyecto):** Documento actual con el contexto, problema, solución y estructura general.

## ⚙️ Uso

1. Instalar las dependencias necesarias:
   ```bash
   pip install openai faiss-cpu sentence-transformers matplotlib pandas numpy
   ```
2. Configurar la API Key de Groq en las variables de entorno.
3. Ejecutar el notebook para probar el agente interactivo.

---
*Desarrollado para la Evaluación Parcial 1*
