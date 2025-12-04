# Tienda Digital con Pedido por WhatsApp (MVP)

> Plataforma de comercio electrónico de bajo coste diseñada para PyMEs. Reemplaza las pasarelas de pago tradicionales con un **mecanismo de pedido directo y automático vía WhatsApp**, garantizando una alta tasa de conversión y eliminando comisiones.

## 1. Enlace al Prototipo Funcional (v0)

Este es el Producto Mínimo Viable (MVP) que demuestra la funcionalidad completa del Frontend y la lógica de negocio antes de la integración con la API REST.

| Módulo | Enlace |
| :--- | :--- |
| **Tienda** | [ENLACE DEL PROTOTIPO] (`https://ezryleal.github.io/MiTienda/`) |

## 2. Problema Resuelto y Propuesta de Valor

| Característica | Propuesta de Valor |
| :--- | :--- |
| **Problema Principal** | La digitalización simple y de bajo costo para PyMEs y emprendedores que buscan vender online sin la complejidad de gastos en integración de pago. |
| **Flujo de Venta** | Genera automáticamente una lista con el pedido vía WhatsApp, eliminando la fricción y el recargo por pagos con Paypal u otros. |
| **Confianza** | Se aprovecha que WhatsApp se puede utilizar como un canal de venta confiable en la región. |
| **Viabilidad (MVP)** | El prototipo v0 demuestra que la solución es creativa y viable al utilizar el `localStorage` para simular la persistencia de los datos. |

## 3. Arquitectura y Stack Tecnológico

Este repositorio contiene la versión MVP (v0). La **Propuesta Técnica Final (v1)** escala el proyecto reemplazando la persistencia local por una arquitectura de microservicios ligera.

### Tecnologías (Stack Final v1)

| Capa | Tecnología | Justificación |
| :--- | :--- | :--- |
| **Frontend** | **Vanilla JavaScript (JS Puro), HTML, CSS** | Se elige por su **bajo *footprint***, velocidad de carga y excelente rendimiento, evitando la sobrecarga de un *framework*. |
| **Backend (API)** | **Node.js con Express** | Se utiliza la pila de JavaScript (Full-Stack JS) para mayor coherencia en el desarrollo y aprovechar la ligereza de Express en la creación de una API RESTful. |
| **Base de Datos** | **SQL (PostgreSQL)** | Los datos de la tienda poseen una naturaleza relacional clara. SQL garantizará la integridad y la consistencia necesaria para la gestión del catálogo. |

### Modelo de Datos (Esquema v1)

| Tabla | Columnas Clave | Referencia en el Prototipo (v0) |
| :--- | :--- | :--- |
| `Admin` | `id, password_hash, store_name, whatsapp_number, address` | Corresponde a `storeConfig` en `admin.js`. |
| `Product` | `id, name, description, price` (decimal), `images` (JSON array) | Corresponde a la matriz `products` en `main.js`. |
| `Order` | `id, client_details, order_summary` (JSON), `created_at` | Registra el pedido generado por WhatsApp. |

## 4. Estructura y Funcionamiento del Código (v0)

| Archivo/Carpeta | Propósito | Funcionalidad Clave |
| :--- | :--- | :--- |
| `index.html` | Vista principal de la tienda (Cliente). | Muestra el catálogo. |
| `admin.html` | Panel de Administración (Vendedor). | Permite el login simple y el **CRUD de productos**. |
| `js/admin.js` | Lógica del Admin. | Maneja la autenticación y la configuración de la tienda, y el CRUD de productos mediante **`localStorage`**. |
| `js/main.js` | Lógica del Cliente. | Carga productos, gestiona el carrito y el **refactor para llamadas `fetch` a la API** será sencillo. |
| `js/cart-view.js` | Lógica de Pedido. | Carga y decodifica el carrito de compras a través del **parámetro URL `data`** para generar el mensaje de WhatsApp. |
| `css/styles.css` | Estilos. | Implementa efectos modernos como el *glassmorphism* y animaciones. |

## 5. Información del Proyecto

* **Nombre del Proyecto:** Tienda Digital con Pedido por WhatsApp
* **Estudiante:** Ezry Adilia Maribeth Leal Franco
* **Carnet:** 202200202
* **Universidad:** Da Vinci
* **Fecha de Entrega:** Guatemala 04 de diciembre de 2025
