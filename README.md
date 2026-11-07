# entregable-1-cicd
Primer entregable del curso de CI/CD

## Integrantes
Santiago Alvarez Peña

## Preguntas

### a. ¿Qué eventos configuraste para disparar tu workflow y por qué?
El evento configurado es **push**, puesto que le estamos indicando a github que cada vez que se ejecute un comando push en la rama main, ejecute nuestro workflow.

### b. ¿Qué sistema operativo utiliza el runner *ubuntu-latest* y por qué puede ejecutar tu workflow aunque tu computadora sea Windows o macOs?¿Qué relación tiene el runner con el shell de los pasos *run*?
El sistema operativo que usa runner es **linux**, especificamente con su distribución de ubuntu en su última versión. Esto permite ejecutar los comandos indicados en el *run*, los cuales se ejecutarán en los servidores de github, por ese motivo, no importa que sistema operativo nativo tengamos.

### c. Menciona al menos 3 acciones pre-construidas del Marketplace de GitHub Actions no mencionadas en este material. Excluye actions/checkout, actions/setup-python, actions/upload-artifact y aws-actions/configure-aws-credentials, aunque alguna solo aparezca como ejemplo conceptual. Describe qué hacen y para qué sirven.

* **actions/cache**: Permite almacenar en caché dependencias críticas y archivos de compilación. Sirven para optimizar radicalmente el tiempo de los pipelines de integración continua (CI).
* **docker/build-push-action**: Aprovecha Docker Buildx para construir imágenes de contenedores optimizadas y publicarlas automáticamente en registros como Docker Hub, GitHub Container Registry (GHCR) o registros de proveedores cloud. Sirve para empaquetar aplicaciones de manera automatizada y estandarizada cada vez que se realiza un commit importante o se genera una etiqueta (tag) en el repositorio.
* **peter-evans/create-pull-request**: Automatiza el proceso de crear Pull Requests (PRs) en un repositorio cuando un workflow modifica o genera archivos de manera programática. Sirve para facilitar la automatización de tareas de mantenimiento del repositorio, permitiendo que un bot proponga cambios de código de forma estructurada para que los desarrolladores humanos simplemente tengan que revisar y aprobar el PR.

### d. ¿Qué es un secreto en GitHub Actions y para qué se usa? ¿Cómo lo usarías en tu workflow?

Un secreto se maneja en github como una variable de entorno encriptada que nos permite almacenar información sensible. Esto se usa para evitar escribir credenciales en texto plano en nuestro archivo YAML. En el workflow se utilizan los secretos invocando a las variables creadas utilizando una sintaxis de contexto.

### e. Reflexiona sobre el uso de GitHub Actions en tu flujo de trabajo diario. ¿Qué tareas automatizarías? ¿Por qué?

Es una herramienta increíble, que nos permite ahorrarnos mucho tiempo y dolores de cabeza. Lo usaría para automatizar despliegues, para hacer pruebas de test y de seguridad. Todo esto lo automatizaría porque hay cosas que una máquina hace mucho más rápido y de manera precisa, nunca dejando de lado la supervisión humana.

En mi campo de ciberseguridad, me abre la mirada a más tecnologías y contextos importantes en donde la seguridad se vuelve algo fundamental, por ejemplo, usar buenas prácticas a la hora de crear el workflow.