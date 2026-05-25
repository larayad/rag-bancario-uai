# Agente RAG Bancario


# Autores:
* Hernán Medina
* Rodrigo González
* Luis Araya

[Abrir Notebook en Google Colab](https://colab.research.google.com/drive/1v-PQBKBmqe6kUlDIDJlTYX9qymjMNIg_?usp=sharing)

Sistema RAG (Retrieval-Augmented Generation) orientado a consulta y análisis de documentación organizacional bancaria.

El proyecto permite consultar hitos, responsables, próximos pasos, iniciativas estratégicas y cambios organizacionales utilizando embeddings, búsqueda semántica y agentes basados en LLM.

---

# Objetivo

Construir un agente corporativo capaz de:

* Consultar documentación interna.
* Recuperar contexto semántico relevante.
* Responder preguntas ejecutivas.
* Identificar responsables e iniciativas.
* Detectar cambios organizacionales.
* Mantener trazabilidad de interacciones.

---

# Arquitectura Implementada

```plaintext
Documentos BANCO
        ↓
Chunking
        ↓
Embeddings OpenAI
        ↓
Chroma Vector DB
        ↓
Similarity Search / KNN
        ↓
Agente Orquestador
        ↓
Workers especializados
        ↓
Agente Fiscalizador
        ↓
Respuesta + referencias documentales
```

---

# Componentes Definidos

| Componente              | Estado |
| ----------------------- | ------ |
| OpenAI API              | ✅      |
| Chroma Vector DB        | ✅      |
| Embeddings              | ✅      |
| Similarity Search / KNN | ✅      |
| Python / Colab          | ✅      |
| Secrets `.env` / Colab  | ✅      |
| Workers lógicos         | ✅      |
| Agente Fiscalizador     | ✅      |

---

# Modelo LLM

## Definido

`gpt-4o-mini`

### Características

* rápido
* económico
* multimodal
* adecuado para prototipos RAG

---

# Arquitectura de Agentes

## Agente Orquestador

Coordina:

* retrieval;
* contexto;
* generación de respuesta.

## Workers

### Worker búsqueda semántica

* recuperación de chunks relevantes.

### Worker resumen ejecutivo

* síntesis ejecutiva.

## Agente Fiscalizador

Valida:

* respuestas vacías;
* ausencia de fuentes;
* posibles datos sensibles;
* preguntas fuera de dominio;
* coherencia básica.

---

# Embeddings y Vector DB

* OpenAI `text-embedding-3-small`
* ChromaDB persistente
* Chunking estructurado Markdown
* Metadata temporal 2024–2026

---

# Evaluación

## Evaluación consultas reales

* 10 preguntas reales
* latencia
* trazabilidad
* fuentes documentales

## Evaluación fuera de dominio

* control de hallucinations
* detección preguntas fuera de alcance
* guardrails básicos

# Evidencias Proyecto RAG Bancario

## Evidencia evaluación consultas reales

Archivo CSV con evaluación de consultas realizadas al agente RAG:

- latencia;
- fuentes utilizadas;
- validación fiscalizador;
- issues detectados;
- comportamiento frente a preguntas reales.

Link:

https://github.com/larayad/rag-bancario-uai/blob/main/outputs/evaluacion_consultas_reales.csv

---

## Evidencia registros en base de datos SQLite

Captura de evidencia del registro persistente de interacciones en la tabla `interactions`.

La tabla almacena:
- timestamp;
- query;
- response;
- fuentes;
- latencia;
- resultados fiscalizador.

Link:

https://github.com/larayad/rag-bancario-uai/blob/main/outputs/Registro%20en%20BD.png

---

## Objetivo de las evidencias

Demostrar:
- funcionamiento del pipeline RAG;
- retrieval semántico;
- trazabilidad;
- persistencia SQL;
- evaluación de respuestas;
- arquitectura multiagente básica;
- control de hallucinations y preguntas fuera de dominio.
---
# Registro SQL

Persistencia SQLite de:

* preguntas;
* respuestas;
* fuentes;
* latencia;
* issues detectados.

---

# Tecnologías

* Python
* LangChain
* OpenAI
* ChromaDB
* SQLite
* Pandas
* Google Colab

---

# Estructura Proyecto

```plaintext
/docs
   /2024
   /2025
   /2026

/outputs
/vector_db

Notebook_Roadmap_RAG_Bancario.ipynb
README.md
requirements.txt
.gitignore
```

---

# Alcance

## Implementado

* RAG corporativo
* Embeddings
* Retrieval semántico
* Workers
* Orquestador
* Fiscalizador
* SQL logging
* Evaluación batch

## Fuera del alcance

* Cloud Run
* Frontend
* Integración Core Bancario
* IAM empresarial
* Producción enterprise

---

# Resultados

* 21 documentos procesados
* Retrieval semántico funcional
* Arquitectura multiagente básica
* Evaluación consultas reales
* Guardrails fuera de dominio
* Fiscalización básica implementada

---


Proyecto académico basado en arquitectura RAG bancaria.
