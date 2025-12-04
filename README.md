# 🛒 Tienda Digital con Pedido por WhatsApp (MVP)

> [cite_start]Plataforma de comercio electrónico de bajo coste diseñada para PyMEs[cite: 13]. [cite_start]Reemplaza las pasarelas de pago tradicionales con un **mecanismo de pedido directo y automático vía WhatsApp** [cite: 14, 17][cite_start], garantizando una alta tasa de conversión y eliminando comisiones[cite: 17].

## 🚀 1. Enlace al Prototipo Funcional (v0)

Este es el Producto Mínimo Viable (MVP) que demuestra la funcionalidad completa del Frontend y la lógica de negocio antes de la integración con la API REST.

| Módulo | Enlace |
| :--- | :--- |
| **Tienda (Cliente)** | [cite_start][ENLACE DEL PROTOTIPO] (Ej. `https://ezryleal.github.io/Tienda/`) [cite: 77] |
| **Panel de Administración** | [ENLACE DEL PROTOTIPO]/admin.html |

## 💡 2. Problema Resuelto y Propuesta de Valor

| Característica | Propuesta de Valor |
| :--- | :--- |
| **Problema Principal** | [cite_start]La digitalización simple y de bajo costo para PyMEs y emprendedores que buscan vender online sin la complejidad de gastos en integración de pago[cite: 13]. |
| **Flujo de Venta** | [cite_start]Genera automáticamente una lista con el pedido vía WhatsApp [cite: 17][cite_start], eliminando la fricción y el recargo por pagos con Paypal u otros[cite: 17]. |
| **Confianza** | [cite_start]Se aprovecha que WhatsApp se puede utilizar como un canal de venta confiable en la región[cite: 19]. |
| **Viabilidad (MVP)** | [cite_start]El prototipo v0 demuestra que la solución es creativa y viable al utilizar el `localStorage` para simular la persistencia de los datos[cite: 20]. |

## ⚙️ 3. Arquitectura y Stack Tecnológico

Este repositorio contiene la versión MVP (v0). [cite_start]La **Propuesta Técnica Final (v1)** escala el proyecto reemplazando la persistencia local por una arquitectura de microservicios ligera[cite: 23].

### Tecnologías (Stack Final v1)

| Capa | Tecnología | Justificación |
| :--- | :--- | :--- |
| **Frontend** | [cite_start]**Vanilla JavaScript (JS Puro), HTML, CSS** [cite: 24, 27] | [cite_start]Se elige por su **bajo *footprint***, velocidad de carga y excelente rendimiento, evitando la sobrecarga de un *framework*[cite: 27]. |
| **Backend (API)** | [cite_start]**Node.js con Express** [cite: 32] | [cite_start]Se utiliza la pila de JavaScript (Full-Stack JS) para mayor coherencia en el desarrollo y aprovechar la ligereza de Express en la creación de una API RESTful[cite: 33]. |
| **Base de Datos** | [cite_start]**SQL (PostgreSQL)** [cite: 38] | [cite_start]Los datos de la tienda poseen una naturaleza relacional clara[cite: 39]. [cite_start]SQL garantizará la integridad y la consistencia necesaria para la gestión del catálogo[cite: 40]. |

### Modelo de Datos (Esquema v1)

| Tabla | Columnas Clave | Referencia en el Prototipo (v0) |
| :--- | :--- | :--- |
| `Admin` | `id, password_hash, store_name, whatsapp_number, address` | [cite_start]Corresponde a `storeConfig` en `admin.js`[cite: 42]. |
| `Product` | `id, name, description, price` (decimal), `images` (JSON array) | [cite_start]Corresponde a la matriz `products` en `main.js`[cite: 42]. |
| `Order` | `id, client_details, order_summary` (JSON), `created_at` | [cite_start]Registra el pedido generado por WhatsApp[cite: 42]. |

## 🛠️ 4. Estructura y Funcionamiento del Código (v0)

| Archivo/Carpeta | Propósito | Funcionalidad Clave |
| :--- | :--- | :--- |
| `index.html` | Vista principal de la tienda (Cliente). | [cite_start]Muestra el catálogo[cite: 16]. |
| `admin.html` | Panel de Administración (Vendedor). | [cite_start]Permite el login simple y el **CRUD de productos**[cite: 15]. |
| `js/admin.js` | Lógica del Admin. | [cite_start]Maneja la autenticación y la configuración de la tienda, y el CRUD de productos mediante **`localStorage`**[cite: 73, 20]. |
| `js/main.js` | Lógica del Cliente. | [cite_start]Carga productos, gestiona el carrito y el **refactor para llamadas `fetch` a la API** será sencillo[cite: 30]. |
| `js/cart-view.js` | Lógica de Pedido. | [cite_start]Carga y decodifica el carrito de compras a través del **parámetro URL `data`** para generar el mensaje de WhatsApp[cite: 73, 75]. |
| `css/styles.css` | Estilos. | [cite_start]Implementa efectos modernos como el *glassmorphism* y animaciones[cite: 29]. |

## 👤 5. Información del Proyecto

* [cite_start]**Nombre del Proyecto:** Tienda Digital con Pedido por WhatsApp [cite: 9]
* [cite_start]**Estudiante:** Ezry Adilia Maribeth Leal Franco [cite: 5]
* [cite_start]**Carnet:** 202200202 [cite: 6]
* [cite_start]**Universidad:** Da Vinci [cite: 3]
* [cite_start]**Fecha de Entrega:** Guatemala 04 de diciembre de 2025 [cite: 7]
