# hf_test1

Aplicación FastAPI mínima ("Hello World") preparada para desplegarse como Space de Hugging Face con Docker.

## Visibilidad y rama
- Público.
- Rama por defecto: no verificado (no se detectó `.git` accesible).

## Stack
- Python 3.9 (imagen `python:3.9`).
- FastAPI y Uvicorn (`uvicorn[standard]`) en `requirements.txt`, sin versiones fijadas.
- Docker.

## Estructura
- `app.py`: instancia `app = FastAPI()` y la ruta `GET /` que devuelve `{"Hello": "World!"}`.
- `requirements.txt`: `fastapi` y `uvicorn[standard]`.
- `Dockerfile`: imagen con usuario `user` (uid 1000), `WORKDIR /app`, arranque con uvicorn en el puerto 7860.
- `README.md`: cabecera de Hugging Face Spaces (no revisado en detalle).

## Comandos
- Instalar: `pip install -r requirements.txt`
- Ejecutar en local: `uvicorn app:app --host 0.0.0.0 --port 7860`
- Construir la imagen: `docker build -t hf_test1 .` (no verificado: no se ejecutó)

## Configuración
- Ninguna variable de entorno ni fichero de configuración.

## Convenciones para agentes
- El puerto 7860 es el que espera Hugging Face Spaces; no cambiarlo sin motivo.
- El Dockerfile ejecuta como usuario no root (uid 1000); mantenerlo.

## Estado
- No hay tests.
- Repositorio de prueba (el nombre lo indica); el código es la plantilla básica.
- Versiones de dependencias sin fijar.
