# DummyJson API — Colección de Pruebas

Colección de endpoints probados con Postman sobre la API pública [DummyJson](https://dummyjson.com), usando la variable `{{baseUrl}}` = `https://dummyjson.com`.

---

## 🔐 Autenticación

### POST /auth/login
**URL:** `{{baseUrl}}/auth/login`

**Body (raw JSON):**
```json
{
  "username": "emilys",
  "password": "emilyspass"
}
```

---

## 📦 Productos

### GET — Get All Products
**URL:** `https://dummyjson.com/products`
**Auth:** Basic Auth (Request Headers)

### GET /products/1 — Buscar por ID
**URL:** `{{baseUrl}}/products/1`

### GET /products/search — Búsqueda por texto
**URL:** `{{baseUrl}}/products/search?q=phone`

**Query Params:**
| Param | Valor |
|---|---|
| q | phone |

### GET /products — Paginación
**URL:** `{{baseUrl}}/products?limit=5`

**Query Params:**
| Param | Valor |
|---|---|
| limit | 5 |

### POST /products/add — Agregar nuevo producto
**URL:** `{{baseUrl}}/products/add`

**Body (raw JSON):**
```json
{
  "title": "Nuevo Producto Test",
  "price": 29.99,
  "stock": 100,
  "category": "smartphones",
  "description": "Producto creado para pruebas de portfolio"
}
```

### PUT /products/1 — Actualizar producto completo
**URL:** `{{baseUrl}}/products/1`

**Body (raw JSON):**
```json
{
  "title": "Producto Actualizado",
  "price": 99.99,
  "stock": 50
}
```

### PATCH /products/1 — Actualizar solo un campo
**URL:** `{{baseUrl}}/products/1`

**Body (raw JSON):**
```json
{
  "price": 19.99
}
```

### DELETE /products/1 — Eliminar producto
**URL:** `{{baseUrl}}/products/1`

**Body (raw text):**
```text
{
  "price": 19.99
}
```

---

## 👤 Usuarios

### POST /users/add — Agregar nuevo usuario
**URL:** `{{baseUrl}}/users/add`

**Body (raw JSON):**
```json
{
  "firstName": "Juan",
  "lastName": "Perez",
  "age": 25,
  "email": "juan.perez@test.com",
  "username": "juanperez99",
  "password": "juan1234"
}
```

---

## 🛒 Carritos

### POST /carts/add — Agregar carrito
**URL:** `{{baseUrl}}/carts/add`

**Body (raw JSON):**
```json
{
  "userId": 1,
  "products": [
    { "id": 1, "quantity": 2 },
    { "id": 3, "quantity": 1 }
  ]
}
```
