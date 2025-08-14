🔷 Front-End
Vue
Framework progresivo de JavaScript para construir interfaces de usuario interactivas y reactivas de manera sencilla.

Vuetify
Framework de componentes UI basado en Material Design para Vue.js. Facilita la creación de interfaces visualmente agradables y responsivas.

Axios
Librería para hacer solicitudes HTTP desde el navegador o Node.js. Se usa para consumir APIs (GET, POST, PUT, DELETE).

i18n en Vuetify
Internacionalización (i18n) permite traducir interfaces a múltiples idiomas. Vuetify puede integrarse con vue-i18n para este propósito.

Pinia
Sistema de manejo de estado oficial para Vue 3 (reemplazo de Vuex). Más sencillo, modular y con mejor integración con Composition API.

Options API en Vue
Forma tradicional de estructurar componentes Vue usando objetos (data, methods, computed, etc.). Contrasta con la Composition API.

🔷 Back-End
Métodos HTTP
Acciones estándar para comunicarse con servidores:

GET: Obtener datos

POST: Enviar nuevos datos / Crear Datos

PUT/PATCH: Actualizar datos existentes

DELETE: Eliminar datos

| Método | Descripción                | Axios                    |
| ------ | -------------------------- | ------------------------ |
| GET    | Obtener datos              | `axios.get(url)`         |
| POST   | Crear nuevo recurso        | `axios.post(url, data)`  |
| PUT    | Actualizar todo el recurso | `axios.put(url, data)`   |
| PATCH  | Actualizar parcialmente    | `axios.patch(url, data)` |
| DELETE | Eliminar un recurso        | `axios.delete(url)`      |

export default function CrudDemo() {
const [posts, setPosts] = useState<Post[]>([]);
const [newPost, setNewPost] = useState({ title: "", body: "" });

// GET - Leer todos los posts
const fetchPosts = async () => {
const res = await fetch("https://jsonplaceholder.typicode.com/posts");
const data = await res.json();
setPosts(data.slice(0, 5)); // Mostrar solo los primeros 5
};

// POST - Crear un nuevo post
const handleCreate = async () => {
const res = await fetch("https://jsonplaceholder.typicode.com/posts", {
method: "POST",
headers: { "Content-Type": "application/json" },
body: JSON.stringify(newPost),
});
const data = await res.json();
alert("Post creado: " + JSON.stringify(data));
fetchPosts();
};

// PUT - Actualizar un post
const handleUpdate = async (id: number) => {
await fetch(`https://jsonplaceholder.typicode.com/posts/${id}`, {
method: "PUT",
headers: { "Content-Type": "application/json" },
body: JSON.stringify({ title: "Actualizado", body: "Nuevo contenido" }),
});
alert("Post actualizado");
fetchPosts();
};

// DELETE - Eliminar un post
const handleDelete = async (id: number) => {
await fetch(`https://jsonplaceholder.typicode.com/posts/${id}`, {
method: "DELETE",
});
alert("Post eliminado");
fetchPosts();
};

useEffect(() => {
fetchPosts();
}, []);

Clases
Estructura de programación orientada a objetos para definir plantillas de objetos. Permiten encapsular datos y comportamientos.

Interfaces
Contratos en lenguajes como TypeScript para definir la estructura que deben tener los objetos (tipado fuerte).

Mappers
Transforman datos entre capas (por ejemplo, de una entidad de base de datos a un DTO). Separan lógica de presentación de lógica de dominio.

Autenticación con JWT
JSON Web Tokens: método para autenticar usuarios de forma segura mediante tokens firmados que se envían en cada solicitud.

CORS (Intercambio de Recursos de Origen Cruzado) es una política de seguridad implementada por los navegadores web.

Su objetivo principal:
Evitar que un sitio web haga peticiones a otro dominio sin permiso, lo cual puede representar un riesgo de seguridad.

🧠 ¿Qué significa "origen cruzado"?
Un origen (origin) está compuesto por:

Protocolo (http o https)

Dominio (example.com)

Puerto (:3000, :8080…)

Ejemplos de origen diferente:

https://midominio.com → origen A

https://api.otrodominio.com → origen B (origen cruzado = "cross-origin")

Si desde el frontend en midominio.com haces un fetch hacia otrodominio.com, estás cruzando orígenes. Aquí es donde CORS entra en acción.

🚫 ¿Qué pasa si CORS no está configurado?
Si el servidor no permite solicitudes desde tu frontend, el navegador bloqueará automáticamente la respuesta, y verás un error en consola

Clean Architecture
Arquitectura de software que separa responsabilidades en capas (entidades, casos de uso, interfaces). Facilita el mantenimiento y la escalabilidad.

Arquitectura Hexagonal
Modelo que aísla la lógica del negocio del resto del sistema mediante puertos y adaptadores. Promueve la independencia de frameworks y tecnologías externas.

Patrones de diseño (Criteria, Singleton)
Criteria: Permite construir consultas dinámicas y reutilizables.

Singleton: Asegura que una clase tenga una única instancia global y proporciona un punto de acceso a ella.

🔷 Otras
Comandos básicos de GIT
git init, git clone, git add, git commit, git push, git pull, git status, etc.
Permiten versionar y gestionar código fuente.

¿Qué es un PR (Pull Request) en GitHub?
Solicitud para fusionar cambios desde una rama a otra. Usado comúnmente en colaboración para revisar y aprobar código antes de integrarlo.

¿Qué es un Fork en GitHub?
Copia de un repositorio a tu cuenta personal para hacer cambios sin afectar el original. Muy útil para contribuir a proyectos open source.
