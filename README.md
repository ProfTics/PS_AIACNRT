# PS_AIACNRT
En este repositorio contiene el desarrollo de la Práctica Supervisada(PS). El desarrollo consiste en el prototipo Funcional de un Agente inteligente para gestionar multas y contemplar la normativa en infracciones, tareas pertenecientes a la CRNT de Gendarmería de Tucumán.

Título: “Agente de Inteligencia Artificial para la gestión de multas e infracciones en la CNRT”.

DOCENTE SUPERVISOR: Prof. Matías Santillán Ahumada

TUTOR INSTITUCIÓN/EMPRESA: Ing. Hadad Salomón, Rosana 

La PS inicia el 15/06/2026 y termina el 21/08/2026

Tecnologías (El Stack Tecnológico está conformado por):

a) Make(Low-code)/Json
b) APIs: Google Gemini, Google Vision, Document AI
c) Base de Datos: Airtable
d) Frontend: Telegram

Instalación: Detalla los pasos exactos para clonar el repositorio y descargar las dependencias necesarias.

Uso: Muestra ejemplos de código o comandos para poner en marcha el proyecto.

Contacto o Autor: andrecosentino17@gmail.com

EN DESARROLLO

# BoByBot:
Este es un bot de Telegram automatizado utilizando la plataforma **Make** (Integromat). 
El bot se encarga realizar 4 tareas:
1: Investigar con Gemini la Página Oficial de la CNRT: https://www.argentina.gob.ar/transporte/cnrt.
2: Consultar el dataset de la Normativa en vigencia.
3: Consultar por DNI/Patente infracciones.
4: Subir multas mediante tecnología OCR.

## 🚀 Cómo Funciona el Flujo
El escenario en Make sigue los siguientes pasos:
1. **Trigger:** [Ej. Recibe un mensaje en el chat de Telegram]
2. **Acción 1:** [Ej. Filtra la información mediante un Router]
3. **Acción 2:** [Ej. Guarda los datos en una hoja de Google Sheets]
4. **Enfoque Final:** [Ej. Envía una confirmación al usuario en Telegram]

## 🛠️ Requisitos Previos
Antes de instalar o replicar el proyecto se requiere:

Git instalado.
Una cuenta activa en Make.
Una cuenta de Telegram.
Un bot creado mediante BotFather.
Una cuenta de Google.
Un proyecto creado en Google Cloud.
Acceso a Google AI Studio para utilizar Gemini.
Una cuenta activa en Airtable.
El archivo blueprint.json exportado desde Make.
Acceso a las APIs utilizadas por el proyecto.

APIs requeridas
Google Gemini API.
Google Cloud Vision API.
Document AI API.
Telegram Bot API.
Airtable API, en caso de utilizar conexiones mediante API.

## ⚙️ Configuración Paso a Paso

### 1. Clonar el Escenario
Si compartes el archivo JSON de Make:
* Descarga el archivo `blueprint.json` incluido en este repositorio.👉
* Ve a tu panel de Make, crea un nuevo escenario y selecciona **Import Blueprint** desde el menú de tres puntos.

### 2. Configurar las Conexiones
* **Módulo de Telegram:** Haz clic en el módulo, añade una nueva conexión y pega tu *Bot Token*. Asegúrate de activar el Webhook.
* **[Módulo 2, ej. Airtable/Gmail]:** Inicia sesión en la plataforma correspondiente para otorgar los permisos de acceso.

### 4. Configurar Telegram en Make
Abre el módulo de Telegram dentro del escenario.
Selecciona Add connection.
Ingresa el token proporcionado por BotFather.
Guarda la conexión.
Configura el módulo encargado de recibir mensajes.
Verifica que el webhook se cree correctamente.
Envía un mensaje de prueba al bot.

### 5. Configurar Airtable
. Crea una cuenta en Airtable.
. Crea una nueva base o duplica la estructura utilizada por el proyecto.
. Configura las tablas requeridas, por ejemplo:
  - Inspectores
  - Sesiones
  - Conductores
  - Vehículos
  - Actas
  - Infracciones
  - Disposiciones
  - Normativa
  - Usuarios

Revisa los nombres de las tablas y campos.
En Make, abre cada módulo de Airtable.
Crea una nueva conexión.
Selecciona la base y la tabla correspondiente.
Actualiza los mapeos de campos.
Realiza una prueba manual de lectura y escritura.


### 6. Configurar Google Cloud Vision
Accede a Google Cloud Console.
Crea o selecciona un proyecto.
Habilita la API de Google Cloud Vision.
Configura las credenciales necesarias.
Restringe las credenciales según el uso previsto.
Configura alertas y límites de consumo.
Añade la conexión correspondiente dentro de Make.


### 7. Configurar Document AI
Accede al proyecto de Google Cloud.
Habilita Document AI API.
Ingresa a la sección de Document AI.
Crea o selecciona un procesador.
Guarda los siguientes datos:
Project ID
Location
Processor ID
Processor Version

### 8. Configurar Gemini
Accede a Google AI Studio.
Genera una clave de API.
Guarda la clave en un lugar seguro.
Abre el módulo de Gemini o HTTP dentro de Make.
Configura la conexión.
Revisa el modelo seleccionado.
Verifica los prompts utilizados por cada ruta.
Ejecuta una consulta de prueba.


### 9. Revisar las conexiones

Después de importar el blueprint, verifica uno por uno los módulos de:

Telegram.
Airtable.
Gemini.
Google Cloud Vision.
Document AI.
HTTP.
JSON.

También debes comprobar:

Identificadores de bases y tablas.
Identificadores de procesadores.
Variables utilizadas por los filtros.
Estructuras JSON.
Webhooks.
Rutas del router.
Mapeos entre módulos.

### 10. Activar el escenario
Guarda todos los cambios.
Selecciona Run once.
Envía un mensaje de prueba al bot.
Revisa la ejecución módulo por módulo.
Corrige cualquier error de conexión o mapeo.
Activa la opción Scheduling.
Comprueba que el escenario permanezca en estado activo.

▶️ Uso
## 📌 Notas de Uso
* Recuerda activar el interruptor de **Scheduling** (Programación) en Make a **ON** para que el bot funcione en tiempo real.
* Revisa la sección de *History* en Make si experimentas errores de formato en los mensajes recibidos.

Una vez activado el escenario, abre el bot en Telegram y ejecuta:

/start

El bot debe presentar el menú principal:
  1. Consultar la página oficial de la CNRT
  2. Consultar normativa vigente
  3. Consultar infracciones
  4. Subir una multa
🧪 Pruebas recomendadas

Antes de utilizar el prototipo completo, ejecuta las pruebas en el siguiente orden:

Recepción de mensajes desde Telegram.
Identificación del inspector.
Creación o actualización de la sesión.
Visualización del menú principal.
Selección de cada opción.
Consulta de información en Airtable.
Consulta mediante Gemini.
Procesamiento de imágenes con Vision.
Procesamiento de documentos con Document AI.
Confirmación de datos extraídos.
Registro de actas.
Respuesta final en Telegram.

Durante las pruebas deben utilizarse datos sintéticos para evitar exponer información personal.
🔐 Seguridad

Para evitar la exposición de credenciales:

No incluyas tokens o claves reales en el repositorio.
No publiques credenciales dentro de blueprint.json.
Revisa el blueprint antes de subirlo.
Utiliza conexiones privadas dentro de Make.
Configura restricciones para las claves de API.
Revoca inmediatamente cualquier token expuesto.
Utiliza datos ficticios o anonimizados durante las pruebas.

💰 Control de consumo

El proyecto debe configurarse para controlar el consumo de operaciones y APIs.

Se recomienda:

Supervisar las operaciones utilizadas en Make.
Configurar alertas de presupuesto en Google Cloud.
Revisar cuotas y límites antes de realizar pruebas.
Evitar procesar repetidamente la misma imagen.
Utilizar imágenes optimizadas.
Implementar rutas alternativas cuando un servicio no esté disponible.
Detener las pruebas cuando se alcance el límite definido para el proyecto.

La disponibilidad gratuita y los límites de cada servicio pueden cambiar. Antes de ejecutar pruebas, consulta siempre la documentación oficial y la configuración de facturación de cada plataforma.

🛠️ Solución de problemas
El bot no recibe mensajes
Verifica que el token de Telegram sea correcto.
Comprueba que el webhook esté activo.
Ejecuta el escenario mediante Run once.
Revisa el historial de ejecuciones de Make.
Confirma que el escenario esté activo.
Airtable devuelve un error
Revisa la conexión.
Verifica los permisos.
Comprueba el identificador de la base.
Confirma el nombre de la tabla.
Actualiza los campos mapeados en Make.
Gemini no responde
Verifica la clave de API.
Confirma que el modelo configurado esté disponible.
Revisa la estructura del prompt.
Comprueba el formato JSON enviado.
Revisa los límites de uso.
El OCR no extrae correctamente el texto
Utiliza una imagen completa y enfocada.
Evita reflejos, sombras y recortes.
Revisa la orientación de la imagen.
Comprueba que la API esté habilitada.
Verifica el módulo que recibe el archivo.
Revisa el tamaño y formato de la imagen.
Document AI devuelve un error
Verifica Project ID, Location y Processor ID.
Confirma que el procesador esté habilitado.
Revisa los permisos de la cuenta utilizada.
Comprueba el tipo y tamaño del documento.
📚 Documentación oficial
Sitio oficial de la CNRT
Documentación de Make
Documentación de blueprints de Make
Documentación de Telegram Bots
Documentación de Cloud Vision
Documentación de Document AI
https://airtable.com
Google AI Studio
⚠️ Limitaciones
El sistema corresponde a un prototipo académico.
Requiere conexión a Internet.
Depende de la disponibilidad de servicios externos.
La precisión del OCR depende de la calidad de la imagen.
La información extraída debe ser validada antes de registrarse.
La interpretación normativa debe verificarse mediante fuentes oficiales.
El prototipo no reemplaza el criterio de los agentes responsables.
No debe utilizarse como única fuente para adoptar decisiones administrativas o legales.

## 👤 Autor
* **Tu Nombre** - [@tu_usuario_telegram](https://t.me)👤 Autora y contacto

Andrea Victoria Cosentino

Correo electrónico:
 andrecosentino17@gmail.com

📄 Licencia

Actualmente el proyecto no tiene una licencia definida.

Antes de reutilizar, distribuir o modificar el contenido, se recomienda solicitar autorización a la autora y a las instituciones involucradas.

📊 Estado del proyecto

🚧 EN DESARROLLO

Las funcionalidades, rutas, estructuras de datos y configuraciones pueden modificarse durante las etapas de prueba, validación y documentación final.

