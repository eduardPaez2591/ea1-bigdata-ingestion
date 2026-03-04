# Proyecto Big Data - Etapa 1 (EA1)

## Ingestión de Datos desde API a SQLite

Este proyecto implementa la etapa inicial de un pipeline de Big Data, enfocándose en la extracción automatizada de datos, almacenamiento en una base de datos relacional y generación de evidencias de auditoría.

### Objetivo

Implementar la ingesta de datos desde la API de tasas de cambio (Exchange Rates), almacenar la información en **SQLite** y generar reportes de muestra y auditoría utilizando **Pandas**.

### Tecnologías y Librerías

- **Lenguaje:** Python 3.10+
- **API:** [Exchange Rates API](https://open.er-api.com/v6/latest/USD) (REST JSON)
- **solicitudes HTTP:**requests
- **Base de Datos:** SQLite3
- **Procesamiento de Datos:** Pandas
- **Automatización:** GitHub Actions (CI/CD)

### Cómo ejecutar

1. Clonar el repositorio
   git clone URL_DEL_REPOSITORIO
   cd NOMBRE_DEL_REPOSITORIO
2. Crear entorno virtual
   En Windows: - python -m venv venv
   venv\Scripts\activate
3. nstalar dependencias
   - pip install -r requirements.txt
4. Ejecutar el script de ingestión
   - python src/ingestion.py

### Al ejecutar el script se crean

- src/datos_api/ingestion.db → Base de datos SQLite
- src/exchage_rate/ingestion.xlsx → Archivo de muestra
- src/static/auditoria/ingestion.txt → Reporte de auditoría

### Automatización con GitHub Actions

Cada push a la rama main ejecuta automáticamente el workflow definido en:
.github/workflows/bigdata.yml
El pipeline realiza:

- Conexión al API
- Extracción de datos
- Inserción en SQLite
- Generación del archivo CSV
- Generación del archivo de auditoría
- Publicación de los archivos como artefactos

### Estructura del Proyecto

```text
[nombre_apellido]
├── .github/workflows/
│   └── bigdata.yml           # Configuración de GitHub Actions
├── src/
│   ├── ingestion.py          # Script principal de ingesta
│   ├── db/                   # Base de datos SQLite (.db)
│   ├── static/auditoria/     # Reporte de auditoría (.txt)
│   └── xlsx/                 # Muestra de datos (.csv/.xlsx)
├── requirements.txt          # Dependencias del proyecto
└── README.md                 # Documentación
```
