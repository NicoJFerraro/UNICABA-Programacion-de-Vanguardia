# 🚀 TableGo - Sistema de Pedidos para Restaurante

**Trabajo Práctico Integrador – Programación de Vanguardia**  
*Licenciatura en Tecnologías Digitales – Universidad de la Ciudad*

---

## 👥 Colaboradores del Proyecto

- **Matías Ibarra**
- **Lucas González**
- **Franco Grillo**
- **Nicolás Ferraro**

---

## 📋 Descripción General

**TableGo** es una aplicación web diseñada para digitalizar y optimizar la operación interna de un restaurante.

### ✨ Funcionalidades Principales:

- ✅ Registrar pedidos digitalmente
- 📊 Visualizar el estado de las mesas
- 🔄 Controlar estados de pedidos
- 📈 Proveer métricas de ventas al administrador

---

## 👥 Roles del Sistema

| Rol | Descripción |
|-----|-------------|
| 🔑 **Administrador** | Gestiona menú, usuarios y mesas; visualiza métricas |
| 👨‍💼 **Mozo** | Atiende mesas, genera pedidos y actualiza estados |
| 👨‍🍳 **Cocinero** | Visualiza pedidos pendientes y marca como listos |
| 👤 **Cliente** | Visualiza menú vía QR y puede iniciar pedidos |

---

## 🎯 Objetivos Funcionales

- 🚫 **Eliminar el uso de papel**
- 🔍 **Mejorar trazabilidad y orden de los pedidos**
- ⚡ **Reducir tiempos y errores**
- 📊 **Proveer métricas en tiempo real**

---

## 🏗️ Arquitectura del Sistema

TableGo implementa una **arquitectura desacoplada**, con frontend y backend comunicados mediante una **API REST**.

### 🖥️ **Frontend**
- **React** - Biblioteca de componentes
- **Vite** - Herramienta de desarrollo 
- **React Router** - Navegación
- **Context API** - Estado global
- **Axios** - Cliente HTTP

### ⚙️ **Backend**
- **Node.js** - Runtime de JavaScript
- **Express** - Framework web
- **Zod** - Validación de esquemas
- **Middlewares** - Arquitectura en capas
- **JWT** - Autenticación

### 🗄️ **Base de Datos**
- **PostgreSQL** - Base de datos relacional
- **Prisma ORM** - Object-Relational Mapping

### 🚀 **Despliegue**
- **Frontend** → Vercel
- **Backend** → Railway
- **Database** → Railway
- **CI/CD** → GitHub Actions

---

## 🧩 Diagrama Lógico del Sistema

```
[Frontend React] ──→ [API REST - Express] ──→ [PostgreSQL - Prisma]
        ↑                         │
        │                         │
        └──────── JWT/Auth ───────┘
```

---

## 🗃️ Modelo de Datos

```
📋 User:       id, name, email, passwordHash, role
🏪 Table:      id, number, status
📂 Category:   id, name
🍽️ Product:    id, name, price, categoryId
📝 Order:      id, tableId, userId, status, createdAt
🛒 OrderItem:  id, orderId, productId, quantity, subtotal
```

---

## 🔄 Flujo Funcional del Sistema

1. 🔐 **El mozo inicia sesión**
2. 🏪 **Selecciona una mesa y crea un pedido**
3. 📨 **El pedido aparece automáticamente en cocina**
4. ✅ **El cocinero marca el pedido como "listo"**
5. 🍽️ **El mozo actualiza a "servido" o "pagado"**
6. 📊 **El administrador visualiza métricas del día**

---

## 📡 Endpoints Principales

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| `POST` | `/api/auth/login` | Login de usuario |
| `POST` | `/api/users` | Crear usuario (admin) |
| `GET` | `/api/tables` | Listar mesas |
| `PATCH` | `/api/tables/:id` | Cambiar estado de mesa |
| `GET` | `/api/orders` | Listar pedidos |
| `POST` | `/api/orders` | Crear pedido |
| `PATCH` | `/api/orders/:id/status` | Actualizar estado de pedido |
| `GET` | `/api/products` | Listar productos |
| `POST` | `/api/products` | Agregar producto |
| `GET` | `/api/metrics/sales` | Ventas del día |

---

## 🔐 Seguridad

- 🎫 **JWT** con expiración
- 🔒 **bcrypt** para hashing
- ✅ **Validación estricta** con Zod
- 🛡️ **Autorización basada en roles**
- 🌐 **CORS restringido**
- ⏰ **Rate limiting**
- 📋 **Logs centralizados**

---

## 🧪 Testing

- **Jest** — Pruebas unitarias
- **Supertest** — Pruebas de integración
- **Postman** — Pruebas de contrato

*Enfoque en lógica de negocio y rutas críticas*

---

## 🔁 CI/CD

**GitHub Actions** para:
- ✅ Lint
- 🧪 Tests
- 🏗️ Build
- 🚀 Deploy

**Deploy automático:**
- **Vercel** (Frontend)
- **Railway** (Backend + DB)

---

## 🗓️ Cronograma

| Semana | Actividades |
|--------|-------------|
| **Semana 1** | Alcance, arquitectura, repositorios |
| **Semana 2** | Modelo de datos y endpoints |
| **Semana 3** | Frontend + conexión API |
| **Semana 4** | Testing, deploy, documentación |

---

## 💡 Conclusiones

**TableGo** digitaliza el proceso interno de un restaurante mediante una **arquitectura moderna, segura y escalable**, integrando conceptos de:

- ⚡ Desarrollo full stack
- 🧪 Testing automatizado
- 🚀 Despliegue continuo
- 🏗️ Buenas prácticas de ingeniería

---

## 🛠️ Tecnologías Utilizadas

### 🖥️ **Frontend**
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)

- **React** - Biblioteca de componentes
- **Vite** - Herramienta de desarrollo
- **React Router** - Navegación
- **Context API** - Estado global
- **Axios** - Cliente HTTP

### ⚙️ **Backend**
![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-404D59?style=for-the-badge)

- **Node.js** - Runtime JavaScript
- **Express** - Framework web
- **Zod** - Validación de esquemas
- **bcrypt** - Hash de contraseñas
- **JWT** - Autenticación

### 🗄️ **Base de Datos**
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)

- **PostgreSQL** - Base de datos relacional
- **Prisma ORM** - Object-Relational Mapping

### 🧪 **Testing**
![Jest](https://img.shields.io/badge/Jest-323330?style=for-the-badge&logo=Jest&logoColor=white)

- **Jest** - Pruebas unitarias
- **Supertest** - Pruebas de integración
- **Postman** - Pruebas de API

### 🚀 **CI/CD y Deploy**
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)

- **GitHub Actions** - CI/CD
- **Vercel** - Deploy frontend
- **Railway** - Deploy backend y DB

### 🛠️ **Herramientas**
- **Git** - Control de versiones
- **GitHub** - Repositorio
- **VS Code** - Editor de código

---

## 📦 Snippets de Código Representativos

### 🔐 Autenticación (Login)
```javascript
import jwt from "jsonwebtoken";
import bcrypt from "bcrypt";
import { prisma } from "../db.js";

export const login = async (req, res) => {
  const { email, password } = req.body;

  const user = await prisma.user.findUnique({ where: { email }});
  if (!user) return res.status(401).json({ message: "Credenciales inválidas" });

  const valid = await bcrypt.compare(password, user.passwordHash);
  if (!valid) return res.status(401).json({ message: "Credenciales inválidas" });

  const token = jwt.sign(
    { id: user.id, role: user.role },
    process.env.JWT_SECRET,
    { expiresIn: "2h" }
  );

  res.json({ token });
};
```

### 📝 Crear Pedido (POST /api/orders)
```javascript
router.post("/", authenticate, async (req, res) => {
  const { tableId, items } = req.body;

  const order = await prisma.order.create({
    data: {
      tableId,
      userId: req.user.id,
      status: "pending",
      items: {
        create: items.map(i => ({
          productId: i.productId,
          quantity: i.quantity,
          subtotal: i.quantity * i.price
        }))
      }
    },
    include: { items: true }
  });

  res.status(201).json(order);
});
```

### 🗄️ Modelo Prisma (Order)
```prisma
model Order {
  id        Int       @id @default(autoincrement())
  tableId   Int
  userId    Int
  status    String
  createdAt DateTime  @default(now())
  items     OrderItem[]

  table     Table     @relation(fields: [tableId], references: [id])
  user      User      @relation(fields: [userId], references: [id])
}
```

### ⚛️ Fetch en React con Axios
```javascript
export async function createOrder(data, token) {
  return axios.post("/api/orders", data, {
    headers: { Authorization: `Bearer ${token}` }
  });
}
```

---

*Desarrollado con 💙 por el equipo de TableGo*

---

# 🚀 TableGo - Restaurant Ordering System

**Integrative Practical Work – Advanced Programming**  
*Bachelor's Degree in Digital Technologies – Universidad de la Ciudad*

---

## 👥 Project Contributors

- **Matías Ibarra**
- **Lucas González**
- **Franco Grillo**
- **Nicolás Ferraro**

---

## 📋 General Description

**TableGo** is a web application designed to digitize and optimize the internal operation of a restaurant.

### ✨ Main Features:

- ✅ Register orders digitally
- 📊 View table status
- 🔄 Control order status
- 📈 Provide sales metrics to the administrator

---

## 👥 System Roles

| Role | Description |
|------|-------------|
| 🔑 **Administrator** | Manages menu, users and tables; views metrics |
| 👨‍💼 **Waiter** | Serves tables, generates orders and updates status |
| 👨‍🍳 **Chef** | Views pending orders and marks them as ready |
| 👤 **Customer** | Views menu via QR and can initiate orders |

---

## 🎯 Functional Objectives

- 🚫 **Eliminate paper usage**
- 🔍 **Improve traceability and order organization**
- ⚡ **Reduce time and errors**
- 📊 **Provide real-time metrics**

---

## 🏗️ System Architecture

TableGo implements a **decoupled architecture**, with frontend and backend communicating through a **REST API**.

### 🖥️ **Frontend**
- **React** - Component library
- **Vite** - Development tool
- **React Router** - Navigation
- **Context API** - Global state
- **Axios** - HTTP client

### ⚙️ **Backend**
- **Node.js** - JavaScript runtime
- **Express** - Web framework
- **Zod** - Schema validation
- **Middlewares** - Layered architecture
- **JWT** - Authentication

### 🗄️ **Database**
- **PostgreSQL** - Relational database
- **Prisma ORM** - Object-Relational Mapping

### 🚀 **Deployment**
- **Frontend** → Vercel
- **Backend** → Railway
- **Database** → Railway
- **CI/CD** → GitHub Actions

---

## 🧩 System Logic Diagram

```
[Frontend React] ──→ [API REST - Express] ──→ [PostgreSQL - Prisma]
        ↑                         │
        │                         │
        └──────── JWT/Auth ───────┘
```

---

## 🗃️ Data Model

```
📋 User:       id, name, email, passwordHash, role
🏪 Table:      id, number, status
📂 Category:   id, name
🍽️ Product:    id, name, price, categoryId
📝 Order:      id, tableId, userId, status, createdAt
🛒 OrderItem:  id, orderId, productId, quantity, subtotal
```

---

## 🔄 System Functional Flow

1. 🔐 **Waiter logs in**
2. 🏪 **Selects a table and creates an order**
3. 📨 **Order automatically appears in kitchen**
4. ✅ **Chef marks the order as "ready"**
5. 🍽️ **Waiter updates to "served" or "paid"**
6. 📊 **Administrator views daily metrics**

---

## 📡 Main Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/auth/login` | User login |
| `POST` | `/api/users` | Create user (admin) |
| `GET` | `/api/tables` | List tables |
| `PATCH` | `/api/tables/:id` | Change table status |
| `GET` | `/api/orders` | List orders |
| `POST` | `/api/orders` | Create order |
| `PATCH` | `/api/orders/:id/status` | Update order status |
| `GET` | `/api/products` | List products |
| `POST` | `/api/products` | Add product |
| `GET` | `/api/metrics/sales` | Daily sales |

---

## 🔐 Security

- 🎫 **JWT** with expiration
- 🔒 **bcrypt** for hashing
- ✅ **Strict validation** with Zod
- 🛡️ **Role-based authorization**
- 🌐 **Restricted CORS**
- ⏰ **Rate limiting**
- 📋 **Centralized logging**

---

## 🧪 Testing

- **Jest** — Unit tests
- **Supertest** — Integration tests
- **Postman** — Contract tests

*Focus on business logic and critical routes*

---

## 🔁 CI/CD

**GitHub Actions** for:
- ✅ Lint
- 🧪 Tests
- 🏗️ Build
- 🚀 Deploy

**Automatic deployment:**
- **Vercel** (Frontend)
- **Railway** (Backend + DB)

---

## 🗓️ Schedule

| Week | Activities |
|------|------------|
| **Week 1** | Scope, architecture, repositories |
| **Week 2** | Data model and endpoints |
| **Week 3** | Frontend + API connection |
| **Week 4** | Testing, deploy, documentation |

---

## 💡 Conclusions

**TableGo** digitalizes the internal process of a restaurant through a **modern, secure and scalable architecture**, integrating concepts of:

- ⚡ Full stack development
- 🧪 Automated testing
- 🚀 Continuous deployment
- 🏗️ Engineering best practices

---

## 🛠️ Technologies Used

### 🖥️ **Frontend**
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)

- **React** - Component library
- **Vite** - Development tool
- **React Router** - Navigation
- **Context API** - Global state
- **Axios** - HTTP client

### ⚙️ **Backend**
![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-404D59?style=for-the-badge)

- **Node.js** - JavaScript runtime
- **Express** - Web framework
- **Zod** - Schema validation
- **bcrypt** - Password hashing
- **JWT** - Authentication

### 🗄️ **Database**
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)

- **PostgreSQL** - Relational database
- **Prisma ORM** - Object-Relational Mapping

### 🧪 **Testing**
![Jest](https://img.shields.io/badge/Jest-323330?style=for-the-badge&logo=Jest&logoColor=white)

- **Jest** - Unit tests
- **Supertest** - Integration tests
- **Postman** - API tests

### 🚀 **CI/CD and Deploy**
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)

- **GitHub Actions** - CI/CD
- **Vercel** - Frontend deploy
- **Railway** - Backend and DB deploy

### 🛠️ **Tools**
- **Git** - Version control
- **GitHub** - Repository
- **VS Code** - Code editor

---

## 📦 Representative Code Snippets

### 🔐 Authentication (Login)
```javascript
import jwt from "jsonwebtoken";
import bcrypt from "bcrypt";
import { prisma } from "../db.js";

export const login = async (req, res) => {
  const { email, password } = req.body;

  const user = await prisma.user.findUnique({ where: { email }});
  if (!user) return res.status(401).json({ message: "Invalid credentials" });

  const valid = await bcrypt.compare(password, user.passwordHash);
  if (!valid) return res.status(401).json({ message: "Invalid credentials" });

  const token = jwt.sign(
    { id: user.id, role: user.role },
    process.env.JWT_SECRET,
    { expiresIn: "2h" }
  );

  res.json({ token });
};
```

### 📝 Create Order (POST /api/orders)
```javascript
router.post("/", authenticate, async (req, res) => {
  const { tableId, items } = req.body;

  const order = await prisma.order.create({
    data: {
      tableId,
      userId: req.user.id,
      status: "pending",
      items: {
        create: items.map(i => ({
          productId: i.productId,
          quantity: i.quantity,
          subtotal: i.quantity * i.price
        }))
      }
    },
    include: { items: true }
  });

  res.status(201).json(order);
});
```

### 🗄️ Prisma Model (Order)
```prisma
model Order {
  id        Int       @id @default(autoincrement())
  tableId   Int
  userId    Int
  status    String
  createdAt DateTime  @default(now())
  items     OrderItem[]

  table     Table     @relation(fields: [tableId], references: [id])
  user      User      @relation(fields: [userId], references: [id])
}
```

### ⚛️ React Fetch with Axios
```javascript
export async function createOrder(data, token) {
  return axios.post("/api/orders", data, {
    headers: { Authorization: `Bearer ${token}` }
  });
}
```

---

*Developed with 💙 by the TableGo team*