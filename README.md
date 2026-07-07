#  MiniGPT HF (Full-Stack) - Alex Perugachi

MiniGPT HF es una aplicación web interactiva de chat educativo conectada a la API de **Hugging Face**. Utiliza un backend en **Node.js con Express** para gestionar de forma segura las peticiones a la API, sirviendo simultáneamente una interfaz frontend estática (HTML, CSS, JS) desde una carpeta `public`.

El asistente está especializado en tres roles clave: Desarrollo Web, Tutoría de Inglés y Depuración de Errores.

---

## Características Principales

* **Asistente Multimodal (Roles):** El backend inyecta dinámicamente *System Prompts* según el modo seleccionado[cite: 7]:
    *  *Profesor de Desarrollo Web*[cite: 7]
    * 🇬🇧 *Tutor de Inglés*[cite: 7]
    *  *Depurador de Errores*[cite: 7]
* **Arquitectura Cliente-Servidor Integrada:** El mismo servidor express proporciona la API (`/api/chat`) y sirve los archivos del frontend estático[cite: 7].
* **Persistencia Local:** El frontend guarda los mensajes en `localStorage`, manteniendo el historial tras recargar la página.
* **Seguridad Básica:** El servidor limita el historial a los últimos 10 mensajes y recorta los mensajes a 3000 caracteres para evitar sobrecargas[cite: 7].
* **Interfaz Moderna e Intuitiva:** Diseño responsivo con gradientes radiales y layouts híbridos.

---

##  Tecnologías Utilizadas

* **Backend:**
    * [Node.js](https://nodejs.org/) (ES Modules)[cite: 5, 7]
    * [Express.js](https://expressjs.com/) (Servidor y API)[cite: 5, 7]
    * `@huggingface/inference` (Cliente oficial de HF)[cite: 5, 7]
    * `dotenv` (Gestión de variables de entorno)[cite: 5, 7]
    * `cors` (Soporte para Cross-Origin Resource Sharing)[cite: 5, 7]
* **Frontend:**
    * HTML5, CSS3, JavaScript (Vainilla)

---

## Estructura del Proyecto

```text
minigpt-hf-backend/
├── .env                # Variables de entorno (Token, Modelo, Puerto)
├── package.json        # Dependencias y scripts del proyecto
├── server.js           # Lógica principal del servidor backend (Express + HF)
└── public/             # Archivos estáticos del frontend
    ├── index.html      # Estructura principal del chat
    ├── styles.css      # Estilos visuales
    └── app.js          # Lógica del cliente