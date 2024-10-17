# Cómo interactuar con tus documentos utilizando Inteligencia Artificial: Creación de un Sistema RAG

## Tabla de Contenidos

1. [¿Qué es un Sistema RAG?](#1-qué-es-un-sistema-rag)
2. [Fundamentos Técnicos del Sistema RAG](#2-fundamentos-técnicos-del-sistema-rag)
   - [2.1. Procesamiento de Lenguaje Natural (NLP)](#21-procesamiento-de-lenguaje-natural-nlp)
   - [2.2. Representación de Texto mediante Vectores (Embeddings)](#22-representación-de-texto-mediante-vectores-embeddings)
   - [2.3. Modelos de Lenguaje Avanzados (GPT-35-gpt-4)](#23-modelos-de-lenguaje-avanzados-gpt-35-gpt-4)
3. [Herramientas Necesarias](#3-herramientas-necesarias)
   - [3.1. Python](#31-python)
   - [3.2. Visual Studio Code (VS Code)](#32-visual-studio-code-vs-code)
   - [3.3. Bibliotecas Esenciales](#33-bibliotecas-esenciales)
4. [Pasos para Implementar un Sistema RAG](#4-pasos-para-implementar-un-sistema-rag)
   - [4.1. Configuración del Entorno de Desarrollo](#41-configuración-del-entorno-de-desarrollo)
   - [4.2. Carga y Preprocesamiento de Documentos](#42-carga-y-preprocesamiento-de-documentos)
   - [4.3. Creación de la Base de Datos Vectorial](#43-creación-de-la-base-de-datos-vectorial)
   - [4.4. Implementación de Consultas en Lenguaje Natural](#44-implementación-de-consultas-en-lenguaje-natural)
   - [4.5. Generación de Respuestas con IA](#45-generación-de-respuestas-con-ia)
5. [Personalización y Optimización del Sistema](#5-personalización-y-optimización-del-sistema)
   - [5.1. Ajuste de Fragmentos de Texto (Chunks)](#51-ajuste-de-fragmentos-de-texto-chunks)
   - [5.2. Uso de Overlap para Contexto](#52-uso-de-overlap-para-contexto)
   - [5.3. Mejora de la Precisión en Respuestas](#53-mejora-de-la-precisión-en-respuestas)
6. [Integración con Interfaces de Usuario](#6-integración-con-interfaces-de-usuario)
   - [6.1. Implementación con Gradio](#61-implementación-con-gradio)
   - [6.2. Implementación con Streamlit](#62-implementación-con-streamlit)
7. [Casos de Uso y Aplicaciones Prácticas](#7-casos-de-uso-y-aplicaciones-prácticas)

---

## 1. ¿Qué es un Sistema RAG?

Un **Sistema RAG (Retrieval-Augmented Generation)** es una arquitectura que combina la recuperación de información y la generación de respuestas asistida por inteligencia artificial. Permite a los usuarios interactuar con sus documentos mediante consultas en lenguaje natural, obteniendo respuestas precisas y contextualizadas basadas en el contenido de dichos documentos.

### Características Principales:

- **Interacción Natural**: Los usuarios pueden hacer preguntas como si conversaran con una persona.
- **Acceso Eficiente a la Información**: Facilita la búsqueda de información específica sin leer documentos completos.
- **Respuestas Contextualizadas**: Utiliza modelos de lenguaje avanzados para generar respuestas coherentes y relevantes.

---

## 2. Fundamentos Técnicos del Sistema RAG

Para entender cómo funciona un sistema RAG, es importante conocer los conceptos técnicos subyacentes.

### 2.1. Procesamiento de Lenguaje Natural (NLP)

El **Procesamiento de Lenguaje Natural (NLP)** es una rama de la IA que se enfoca en la interacción entre computadoras y humanos a través del lenguaje natural.

- **Análisis Sintáctico**: Estudio de la estructura gramatical del texto.
- **Análisis Semántico**: Comprensión del significado y contexto del texto.
- **Aplicaciones**: Traducción automática, análisis de sentimientos, chatbots.

### 2.2. Representación de Texto mediante Vectores (Embeddings)

Los **Embeddings** son representaciones numéricas de palabras o frases que capturan su significado semántico.

- **Vectorización**: Cada palabra se representa como un vector en un espacio multidimensional.
- **Similitud Semántica**: Palabras con significados similares tienen vectores cercanos.
- **Modelos Comunes**: Word2Vec, GloVe, FastText.

### 2.3. Modelos de Lenguaje Avanzados (GPT-3.5, GPT-4)

Los **Modelos Generativos Pre-entrenados (GPT)** son modelos de IA que pueden generar texto coherente y contextualmente relevante.

- **GPT-3.5 y GPT-4**: Versiones avanzadas con mayor capacidad para comprender y generar lenguaje natural.
- **Capacidades**:
  - Responder preguntas.
  - Traducir textos.
  - Resumir documentos.
- **Uso en RAG**: Generan respuestas basadas en información recuperada de los documentos.

---

## 3. Herramientas Necesarias

Para implementar un sistema RAG, se requieren ciertas herramientas de software.

### 3.1. Python

**Python** es un lenguaje de programación ampliamente utilizado en IA y NLP debido a sus bibliotecas y comunidad activa.

- **Instalación**: Descargar desde [python.org](https://www.python.org/downloads/).
- **Versiones Recomendadas**: Python 3.7 o superior.

### 3.2. Visual Studio Code (VS Code)

**Visual Studio Code** es un editor de código fuente que ofrece soporte para múltiples lenguajes y extensiones.

- **Características**:
  - Depurador integrado.
  - Terminal integrada.
  - Extensiones para Python.

### 3.3. Bibliotecas Esenciales

- **LangChain**: Para construir cadenas de procesamiento con modelos de lenguaje.
- **OpenAI**: Para acceder a modelos como GPT-3.5 y GPT-4.
- **FAISS**: Biblioteca de Facebook para búsquedas eficientes en bases de datos vectoriales.
- **Pandas**: Para manipulación y análisis de datos.

---

## 4. Pasos para Implementar un Sistema RAG

A continuación, se detallan los pasos para desarrollar un sistema RAG funcional.

### 4.1. Configuración del Entorno de Desarrollo

#### 4.1.1. Instalación de Python y Entorno Virtual

- **Crear un Entorno Virtual**:

  ```bash
  python -m venv env_rag
  ```

- **Activar el Entorno Virtual**:

  - En Windows:

    ```bash
    env_rag\Scripts\activate
    ```

  - En macOS/Linux:

    ```bash
    source env_rag/bin/activate
    ```

#### 4.1.2. Instalación de Dependencias

- **Instalar Bibliotecas**:

  ```bash
  pip install langchain openai faiss-cpu pandas gradio streamlit
  ```

### 4.2. Carga y Preprocesamiento de Documentos

#### 4.2.1. Cargar Documentos

- **Utilizar DirectoryLoader de LangChain**:

  ```python
  from langchain.document_loaders import DirectoryLoader

  loader = DirectoryLoader('docs/', glob='**/*.pdf')
  documents = loader.load()
  ```

#### 4.2.2. Dividir Documentos en Fragmentos (Chunks)

- **Configurar el Divisor de Texto**:

  ```python
  from langchain.text_splitter import RecursiveCharacterTextSplitter

  text_splitter = RecursiveCharacterTextSplitter(chunk_size=1000, chunk_overlap=200)
  texts = text_splitter.split_documents(documents)
  ```

### 4.3. Creación de la Base de Datos Vectorial

#### 4.3.1. Generar Embeddings

- **Utilizar OpenAIEmbeddings**:

  ```python
  from langchain.embeddings import OpenAIEmbeddings

  embeddings = OpenAIEmbeddings()
  ```

#### 4.3.2. Crear la Base de Datos con FAISS

- **Construir el Vectorstore**:

  ```python
  from langchain.vectorstores import FAISS

  vectorstore = FAISS.from_documents(texts, embeddings)
  ```

### 4.4. Implementación de Consultas en Lenguaje Natural

#### 4.4.1. Configurar el Modelo de Lenguaje

- **Seleccionar el Modelo**:

  ```python
  from langchain.llms import OpenAI

  llm = OpenAI(model_name='gpt-3.5-turbo')
  ```

#### 4.4.2. Crear la Cadena de Preguntas y Respuestas

- **Configurar RetrievalQA**:

  ```python
  from langchain.chains import RetrievalQA

  qa_chain = RetrievalQA.from_chain_type(llm=llm, chain_type='stuff', retriever=vectorstore.as_retriever())
  ```

### 4.5. Generación de Respuestas con IA

#### 4.5.1. Implementar el Bucle de Consulta

- **Código de Interacción**:

  ```python
  while True:
      query = input("Ingrese su pregunta (o 'salir' para terminar): ")
      if query.lower() == 'salir':
          break
      answer = qa_chain.run(query)
      print(f"Respuesta: {answer}\n")
  ```

---

## 5. Personalización y Optimización del Sistema

Para mejorar la eficacia del sistema, es posible realizar ajustes y optimizaciones.

### 5.1. Ajuste de Fragmentos de Texto (Chunks)

- **Modificar chunk_size y chunk_overlap**:

  ```python
  text_splitter = RecursiveCharacterTextSplitter(chunk_size=1500, chunk_overlap=300)
  ```

- **Impacto**: Fragmentos más grandes pueden mantener mejor el contexto, pero pueden aumentar el tiempo de procesamiento.

### 5.2. Uso de Overlap para Contexto

- **Overlap**: Permite que los fragmentos compartan información, manteniendo el contexto entre ellos.

- **Ejemplo**:

  ```python
  chunk_overlap=250  # Incrementa el solapamiento
  ```

### 5.3. Mejora de la Precisión en Respuestas

- **Ajustar el Prompt**:

  ```python
  qa_chain = RetrievalQA.from_chain_type(
      llm=llm, 
      chain_type='stuff', 
      retriever=vectorstore.as_retriever(), 
      return_source_documents=True
  )
  ```

- **Incluir Contexto Adicional**: Proporcionar instrucciones más detalladas al modelo.

---

## 6. Integración con Interfaces de Usuario

Para mejorar la experiencia del usuario, se pueden integrar interfaces gráficas.

### 6.1. Implementación con Gradio

#### 6.1.1. Instalación

- **Instalar Gradio**:

  ```bash
  pip install gradio
  ```

#### 6.1.2. Código de Implementación

- **Crear la Interfaz**:

  ```python
  import gradio as gr

  def answer_question(question):
      return qa_chain.run(question)

  iface = gr.Interface(fn=answer_question, inputs="text", outputs="text", title="Chat con tus Documentos")
  iface.launch()
  ```

### 6.2. Implementación con Streamlit

#### 6.2.1. Instalación

- **Instalar Streamlit**:

  ```bash
  pip install streamlit
  ```

#### 6.2.2. Código de Implementación

- **Crear la Aplicación**:

  ```python
  import streamlit as st

  st.title("Chat con tus Documentos")

  query = st.text_input("Ingrese su pregunta:")
  if query:
      answer = qa_chain.run(query)
      st.write(f"Respuesta: {answer}")
  ```

- **Ejecutar la Aplicación**:

  ```bash
  streamlit run app.py
  ```

---

## 7. Casos de Uso y Aplicaciones Prácticas

- **Empresas**: Gestión de manuales internos, políticas y procedimientos.
- **Educación**: Acceso rápido a libros de texto y materiales de estudio.
- **Legal**: Búsqueda eficiente en leyes y regulaciones.
- **Investigación**: Análisis de grandes volúmenes de literatura científica.
