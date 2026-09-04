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
Este es un bot de Telegram automatizado utilizando la plataforma **Make** (Integromat). El bot se encarga realizar 4 tareas:
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
Antes de replicar este escenario, necesitas:
* Una cuenta activa en [Make](https://make.com).
* Un token de bot de Telegram (búscalo creando tu bot con [@BotFather](https://t.me)).
* Una cuenta en google Workspace.
* Con la misma cuenta en google Workspace, generar un cuenta en Google Cloud para obtener las APIs.
* APIs: Google Cloud Vision, Docuement AI
* Token: Telegram, Google Studio AI(Gemini), Google CLoud Vision.
* EL modulo dentro de Make de Document AI debes configurar:
* Crear una cuenta en Airtable, recomiendo usar la misma de Gooogle Workspace.

## ⚙️ Configuración Paso a Paso

### 1. Clonar el Escenario
Si compartes el archivo JSON de Make:
* Descarga el archivo `blueprint.json` incluido en este repositorio.👉
* Ve a tu panel de Make, crea un nuevo escenario y selecciona **Import Blueprint** desde el menú de tres puntos.

### 2. Configurar las Conexiones
* **Módulo de Telegram:** Haz clic en el módulo, añade una nueva conexión y pega tu *Bot Token*. Asegúrate de activar el Webhook.
* **[Módulo 2, ej. Airtable/Gmail]:** Inicia sesión en la plataforma correspondiente para otorgar los permisos de acceso.

## 📌 Notas de Uso
* Recuerda activar el interruptor de **Scheduling** (Programación) en Make a **ON** para que el bot funcione en tiempo real.
* Revisa la sección de *History* en Make si experimentas errores de formato en los mensajes recibidos.

## 👤 Autor
* **Tu Nombre** - [@tu_usuario_telegram](https://t.me)
