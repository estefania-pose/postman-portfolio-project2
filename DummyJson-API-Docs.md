## 🧪 Pruebas de API con Postman — DummyJson

En esta sección se documentan las pruebas de integración realizadas sobre la API pública **DummyJson**. El archivo de la colección en formato JSON está disponible en este repositorio para ser descargado e importado directamente en Postman.

A continuación, podés desplegar cada endpoint para revisar la configuración de la solicitud, los datos enviados y las evidencias de ejecución con sus respectivos códigos de estado HTTP.

---

### 🔑 Autenticación

<details>
  <summary><b>POST</b> /auth/login — Autenticación de usuario</summary>

  * **Descripción:** Envía credenciales de usuario para validar el acceso y generar un token de autenticación.
  * **Cuerpo de la solicitud (Body):**
    ```json
    {
      "username": "emilys",
      "password": "emilyspass"
    }
    ```
  * **Resultado esperado:** `200 OK` junto con el token Bearer y los datos del perfil.
  * **Evidencia de ejecución:**
  <img width="969" height="481" alt="post autenticacion" src="https://github.com/user-attachments/assets/d7a299b1-09e0-447b-83d7-99c5d30bbbb3" />


</details>

---

### 📦 Módulo de Productos

<details>
  <summary><b>GET</b> /products — Obtener todos los productos</summary>

  * **Descripción:** Recupera el listado completo de los productos disponibles en la plataforma.
  * **Autenticación:** Basic Auth.
  * **Resultado esperado:** `200 OK` con el array completo de ítems.
  * **Evidencia de ejecución:**
    <img width="956" height="908" alt="Get All Products" src="https://github.com/user-attachments/assets/1096cb46-49f6-4acf-a43b-d225e020f801" />


</details>

<details>
  <summary><b>GET</b> /products/1 — Obtener producto por ID</summary>

  * **Descripción:** Recupera el detalle específico de un único producto utilizando su identificador en la URL.
  * **Resultado esperado:** `200 OK` con la información exclusiva del producto solicitado.
  * **Evidencia de ejecución:**
   <img width="977" height="704" alt="get products 1" src="https://github.com/user-attachments/assets/7341b810-82ca-483e-b828-26436291c84c" />


</details>

<details>
  <summary><b>GET</b> /products/search?q=phone — Buscar productos</summary>

  * **Descripción:** Realiza una búsqueda filtrada en el catálogo mediante un parámetro de consulta (`q`).
  * **Query Params:** `q = phone`
  * **Resultado esperado:** `200 OK` con las coincidencias encontradas.
  * **Evidencia de ejecución:**
    <img width="970" height="652" alt="get products search" src="https://github.com/user-attachments/assets/0dbcbade-7016-40af-b6ea-ed01c30bf9e7" />


</details>

<details>
  <summary><b>GET</b> /products?limit=5 — Paginación de catálogo</summary>

  * **Descripción:** Limita la cantidad de resultados devueltos por la API para optimizar la carga de datos.
  * **Query Params:** `limit = 5`
  * **Resultado esperado:** `200 OK` conteniendo exactamente un máximo de 5 productos.
  * **Evidencia de ejecución:**
    <img width="984" height="576" alt="get products limit" src="https://github.com/user-attachments/assets/ad134762-5277-4e03-89a7-3b6652da75f7" />


</details>

<details>
  <summary><b>POST</b> /products/add — Agregar nuevo producto</summary>

  * **Descripción:** Simula la creación de un nuevo artículo dentro del sistema.
  * **Cuerpo de la solicitud (Body):**
    ```json
    {
      "title": "Nuevo Producto Test",
      "price": 29.99,
      "stock": 100,
      "category": "smartphones",
      "description": "Producto creado para pruebas de portfolio"
    }
    ```
  * **Resultado esperado:** `201 Created` o `200 OK` devolviendo el objeto creado con un ID asignado.
  * **Evidencia de ejecución:**
   <img width="976" height="600" alt="post product add" src="https://github.com/user-attachments/assets/99978c8d-e4b3-456c-8dd9-1c95c234d02a" />


</details>

<details>
  <summary><b>PUT</b> /products/1 — Actualizar producto completo</summary>

  * **Descripción:** Reemplaza y actualiza la totalidad de los datos de un producto existente.
  * **Cuerpo de la solicitud (Body):**
    ```json
    {
      "title": "Producto Actualizado",
      "price": 99.99,
      "stock": 50
    }
    ```
  * **Resultado esperado:** `200 OK` reflejando los campos modificados.
  * **Evidencia de ejecución:**
    <img width="969" height="589" alt="put actualizar producto completo" src="https://github.com/user-attachments/assets/d1fea98c-7635-4868-b1ae-9ca2488e7dc8" />


</details>

<details>
  <summary><b>PATCH</b> /products/1 — Actualizar solo un campo</summary>

  * **Descripción:** Modifica de manera parcial un atributo específico del recurso sin alterar el resto.
  * **Cuerpo de la solicitud (Body):**
    ```json
    {
      "price": 19.99
    }
    ```
  * **Resultado esperado:** `200 OK` con el valor del precio actualizado.
  * **Evidencia de ejecución:**
    <img width="976" height="608" alt="patch actualizar solo un campo" src="https://github.com/user-attachments/assets/1b1c4eb8-cf4f-484c-bcb4-b8e378e79723" />


</details>

<details>
  <summary><b>DELETE</b> /products/1 — Eliminar producto</summary>

  * **Descripción:** Solicita la baja de un producto del catálogo por medio de su ID.
  * **Resultado esperado:** `200 OK` confirmando la eliminación física o lógica del ítem (propiedad `isDeleted: true`).
  * **Evidencia de ejecución:**
    <img width="973" height="609" alt="delete product" src="https://github.com/user-attachments/assets/24154931-0b51-4364-b2c0-0e6b829a5ee9" />


</details>

---

### 👤 Módulo de Usuarios

<details>
  <summary><b>POST</b> /users/add — Registrar nuevo usuario</summary>

  * **Descripción:** Da de alta un nuevo perfil de usuario en la base de datos de la aplicación.
  * **Cuerpo de la solicitud (Body):**
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
  * **Resultado esperado:** `201 Created` o `200 OK` con el ID del nuevo usuario registrado.
  * **Evidencia de ejecución:**
   <img width="973" height="717" alt="post user add" src="https://github.com/user-attachments/assets/5578c604-1691-40b3-b488-ee44d8a34dd2" />


</details>

---

### 🛒 Módulo de Carritos

<details>
  <summary><b>POST</b> /carts/add — Agregar elementos al carrito</summary>

  * **Descripción:** Registra una nueva operación de compra asignando productos específicos al carrito de un usuario.
  * **Cuerpo de la solicitud (Body):**
    ```json
    {
      "userId": 1,
      "products": [
        { "id": 1, "quantity": 2 },
        { "id": 3, "quantity": 1 }
      ]
    }
    ```
  * **Resultado esperado:** `200 OK` con el desglose de totales, cantidades y el ID del carrito generado.
  * **Evidencia de ejecución:**
    <img width="978" height="498" alt="post carts add" src="https://github.com/user-attachments/assets/150ce151-4097-47b3-95e1-219832115199" />


</details>
