# Automatización de E-mails Bancarios a Google Sheets

Una herramienta de automatización en **Python** que extrae información de movimientos bancarios desde correos electrónicos y los registra automáticamente en una hoja de cálculo de **Google Sheets**.  
Ideal para llevar un control financiero personal o de pequeñas empresas de forma rápida y sin intervención manual.

---

## ✨ Características Principales

- **Extracción de Datos de Correos Electrónicos**:  
  Se conecta a una cuenta al correo del usuario mediante al servidor **IMAP**, autentica sesión, busca correos de remitentes bancarios específicos.

- **Análisis Inteligente**:  
  Utiliza expresiones regulares para identificar y extraer el **monto**, la **moneda** y el **tipo de movimiento** (débito/crédito).

- **Detección de Duplicados**:  
  Evita la inserción de datos repetidos en la hoja de cálculo mediante dar un nro. de Id a cada mail leído

- **Integración con Google Sheets**:  
  Utiliza la **API de Google Sheets** para almacenar los datos automáticamente.

- **Ejecución Continua**:  
  El script principal se ejecuta en un bucle para procesar nuevos correos a intervalos definidos por el usuario.

---

## 🛠 Tecnologías y Librerías Utilizadas

- **Python 3**
- `python-dotenv`
- `imaplib`
- `google-api-python-client`
- `google-auth-httplib2`
- `haslib`

---

## 📂 Estructura del Proyecto

- **`index.py`** → Script principal que coordina todo el flujo.  
- **`imap_reader.py`** → Conexión IMAP y lectura de correos electrónicos.  
- **`sheets_writer.py`** → Conexión con la API de Google Sheets y escritura de datos.  

---

## ⚙️ Configuración y Requisitos

### 1️⃣ Habilitar la API de Google Sheets
- Ir a la [documentación oficial de Google Sheets API](https://developers.google.com/sheets/api/quickstart/python) y habilitar la API.  
- Crear credenciales de **cuenta de servicio** y descargar el archivo `service_account.json`.  

---

### 🚀 Uso
Una vez configurado el proyecto:

1. Colocar las credenciales (`service_account.json`) en la carpeta raíz.

2. Verificar que el archivo `.env` esté correctamente configurado.

3. Ejecutar el script principal:

`python index.py`

---------

### 🗺️ Diagrama de Flujo
flowchart TD
    A[Correo IMAP] --> B[Lectura de E-mails - imap_reader.py]
    B --> C[Procesamiento de Datos - Regex y lógica]
    C --> D[Verificación de duplicados]
    D --> E[Envío a Google Sheets - sheets_writer.py]
    E --> F[Google Sheets Actualizado]

---

## 👥 Equipo del Proyecto

- **Lucas Lopez** → [GitHub](https://github.com/LucasLopezC)  
- **Cristobal Cocuesta** → [GitHub](https://github.com/cocucris)  
- **Lujan Ibarra** → [GitHub](https://github.com/lujanib)  
- **Fiorella Escobar** → [GitHub](https://github.com/usuario-fiorella)  
- **Eduardo** → [GitHub](https://github.com/usuario-eduardo)  
- **Adan** → [GitHub](https://github.com/usuario-adan)  

---

### Configurar Variables de Entorno
- Crear un archivo `.env` en la raíz del proyecto con el siguiente contenido:

```env
EMAIL_USER=tu_correo@example.com
EMAIL_PASS=tu_contraseña
REMITENTES_BANCOS=correo1@banco.com,correo2@banco.com
SPREADSHEET_ID=tu_spreadsheet_id
SHEET_RANGE=Hoja1!A1
GOOGLE_APPLICATION_CREDENTIALS=service_account.json

