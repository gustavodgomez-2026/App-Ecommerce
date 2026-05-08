# App-Ecommerce
App ecommerce (Actividad 4)
```markdown
# mi-app

## Descripción del Proyecto
Este proyecto es una aplicación web interactiva de e-commerce con IA, construida para permitir a los usuarios categorizar imágenes de productos y obtener información relevante a través de un asistente de chat impulsado por inteligencia artificial. La aplicación integra funcionalidades de clasificación de imágenes, procesamiento de lenguaje natural y una experiencia de usuario que simula la interacción en una plataforma de comercio electrónico, incluyendo la selección de productos y la adición (simulada) al carrito.

## Tecnologías Utilizadas
*   **Frontend/Interfaz:** Gradio (gr.Blocks, gr.Image, gr.Textbox, gr.Button, gr.Chatbot, gr.CheckboxGroup) para la construcción de la interfaz de usuario.
*   **Clasificación de Imágenes:** Modelos de Hugging Face Transformers (`google/vit-base-patch16-224`) para la categorización automática de imágenes de productos.
*   **Modelo de Lenguaje (LLM):** Google Gemini (`gemini-2.5-flash`) para las capacidades de conversación del chatbot.
*   **Manejo de Datos:** La librería Pandas se utiliza para la gestión y manipulación de la base de datos de productos.
*   **Entorno de Desarrollo y Despliegue:** Google Colab para el desarrollo inicial y Hugging Face Spaces / Streamlit Cloud para el despliegue online.

## Funcionalidades Clave
La aplicación se compone de los siguientes módulos principales:

### 1. Base de Datos de Productos
Una colección predefinida de productos (laptops, monitores, periféricos) con detalles como modelo, precio, stock y descripción, que sirve como fuente de información para el asistente de chat.

### 2. Módulo de Categorización de Imágenes
Permite a los usuarios subir una imagen de un producto. Un modelo de IA clasifica la imagen en una de las categorías predefinidas (`laptop`, `monitor`, `perifericos`). El usuario puede borrar la imagen o usar la categoría predicha para interactuar con el chatbot.

### 3. Asistente de Información de Productos (Chatbot)
Un asistente conversacional que interactúa con el usuario y proporciona información basada en el contexto:
*   **Respuestas Generales:** Utiliza Google Gemini para responder preguntas abiertas.
*   **Respuestas Contextualizadas:** Si una imagen ha sido categorizada, el chatbot ofrece listar los productos de esa categoría.
*   **Selección de Productos:** Presenta los modelos disponibles de una categoría en un formato seleccionable (checkboxes) y simula la adición de productos al carrito.

## Instalación y Ejecución Local

### Prerrequisitos
*   Python 3.8+
*   Clave API de Google Gemini (configurada como secreto de entorno `GEMINI_API_KEY`)

### Pasos
1.  Clona el repositorio:
    ```bash
    git clone https://github.com/tu-usuario/mi-app.git
    cd mi-app
    ```
2.  Crea un entorno virtual (recomendado):
    ```bash
    python -m venv venv
    source venv/bin/activate # En Windows usa `venv\Scripts\activate`
    ```
3.  Instala las dependencias:
    ```bash
    pip install -r requirements.txt
    ```
    (Asegúrate de que `requirements.txt` contenga `gradio==3.50.2`, `transformers`, `accelerate`, `torch`, `google-generativeai`, `pandas`)
4.  Configura tu clave API de Gemini:
    Asegúrate de tener tu `GEMINI_API_KEY` configurada como una variable de entorno. Por ejemplo:
    ```bash
    export GEMINI_API_KEY='tu_clave_aqui' 
    # O si usas Colab/Hugging Face Spaces, configura como un 'Secret'.
    ```
5.  Ejecuta la aplicación:
    ```bash
    python app.py
    ```
    (Si estás en Colab, simplemente ejecuta las celdas del notebook).

## Despliegue Online

La aplicación está diseñada para ser fácilmente desplegable en plataformas como Hugging Face Spaces o Streamlit Cloud.

### Hugging Face Spaces
1.  Crea un nuevo Space en Hugging Face.
2.  Conecta tu repositorio GitHub.
3.  Asegúrate de que tu `requirements.txt` esté correcto.
4.  Configura `GEMINI_API_KEY` como un secreto de entorno en tu Space.

**Link a la App Desplegada:** [URL de tu aplicación desplegada aquí]

## Capturas de Pantalla
(Añade aquí capturas de pantalla de tu aplicación funcionando, mostrando la categorización de imágenes, la interacción del chatbot y la selección de productos).

**Ejemplo:**

![Captura de pantalla de la interfaz principal]

![Captura de pantalla de la interacción del chatbot]

```
