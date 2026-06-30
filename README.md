[README.md](https://github.com/user-attachments/files/29514466/README.md)
# Postman Portfolio — Proyecto 2: DummyJson API

Proyecto de práctica enfocado en testing y consumo de APIs REST usando **Postman**, sobre la API pública [DummyJson](https://dummyjson.com).

## 🎯 Objetivo

Practicar y documentar el uso de los principales métodos HTTP (GET, POST, PUT, PATCH, DELETE) contra una API real, incluyendo autenticación, manejo de query params, paginación y envío de bodies en distintos formatos.

## 🛠️ Tecnologías / Herramientas

- **Postman** — diseño, ejecución y documentación de requests.
- **DummyJson API** — API pública de pruebas (productos, usuarios, carritos, autenticación).

## 📂 Contenido del repositorio

| Archivo | Descripción |
|---|---|
| `DummyJson.postman_collection.json` | Colección de Postman (formato v2.1) lista para importar, con todos los requests, bodies y la variable `baseUrl`. |
| `DummyJson-API-Docs.md` | Documentación legible de cada endpoint: método, URL, query params y body de ejemplo. |

## 🔍 Endpoints cubiertos

- **Autenticación:** `POST /auth/login`
- **Productos:**
  - `GET /products` — listado completo
  - `GET /products/{id}` — búsqueda por ID
  - `GET /products/search?q=` — búsqueda por texto
  - `GET /products?limit=` — paginación
  - `POST /products/add` — alta de producto
  - `PUT /products/{id}` — actualización completa
  - `PATCH /products/{id}` — actualización parcial
  - `DELETE /products/{id}` — eliminación
- **Usuarios:** `POST /users/add`
- **Carritos:** `POST /carts/add`

## ▶️ Cómo importar la colección

1. Descargá el archivo `DummyJson.postman_collection.json` de este repositorio.
2. En Postman: **Import** → seleccioná el archivo (o arrastralo).
3. La colección se carga con todos los requests ya configurados, usando la variable `baseUrl = https://dummyjson.com`.

## 📌 Notas

Este proyecto forma parte de mi portfolio de práctica en testing manual y exploratorio de APIs REST.
