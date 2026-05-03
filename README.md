# Checkout new version:
deployment link: https://feasto-app-latest.onrender.com/

repo link: https://github.com/prakhar-5447/feasto-frontend

# 🍹 Juicy-N-Yummy

> A full-stack restaurant aggregator and food delivery platform that enhances the dining experience by providing menus, reviews, and location-based restaurant discovery.

![Home Screenshot](https://github.com/prakhar-5447/Juicy-N-Yummy/raw/master/screenshots/home.png)

![Angular](https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-3F3AFB?style=for-the-badge&logo=mongodb&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![Express](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)
![Netlify](https://img.shields.io/badge/Netlify-181818?style=for-the-badge&logo=netlify&logoColor=white)
![License: AGPL-3.0](https://img.shields.io/badge/License-AGPL--3.0-blue?style=for-the-badge)

---

## 📖 About

**Juicy-N-Yummy** is an innovative platform designed to enhance the dining experience. It aggregates information from a wide range of restaurants, allowing users to explore detailed menus, read user reviews, and discover new dining options tailored to their preferences. The platform acts as a one-stop destination for restaurant information and food delivery — streamlining the process of finding and ordering from local eateries.

---

## ✨ Features

- **Dashboard** — Manage and view data through a user-friendly dashboard with analytics and insights for better decision-making.
- **Item Management** — Easily add new items, edit existing ones, and manage inventory. Keep listings up-to-date and organized.
- **Reviews & Feedback** — Allow users to leave reviews and feedback. Monitor and manage reviews to maintain quality and address user concerns.
- **Location-Based Discovery** — Find restaurants and services based on your location. Explore nearby options and get relevant recommendations.
- **Authentication** — Secure user registration and login with JWT-based authentication.

---

## 🛠️ Tech Stack

### Frontend
| Technology | Version | Purpose |
|---|---|---|
| Angular | ~13.3.0 | Frontend SPA framework |
| TypeScript | ~4.6.2 | Strongly-typed language for Angular |
| Angular Material | ^13.3.7 | UI component library |
| Angular CDK | ^13.3.7 | Component development kit |
| TailwindCSS | ^3.0.24 | Utility-first CSS styling |
| RxJS | ~7.5.0 | Reactive programming / HTTP observables |
| Angular Router | ~13.3.0 | Client-side page routing |
| Angular Forms | ~13.3.0 | Reactive and template-driven forms |
| Zone.js | ~0.11.4 | Change detection |

### Backend
| Technology | Purpose |
|---|---|
| Node.js | JavaScript runtime for the server |
| Express.js | Web framework for REST API |
| MongoDB | NoSQL database for storing app data |
| Mongoose | ODM library for MongoDB schema modeling |
| JSON Web Token (JWT) | Stateless authentication |
| dotenv | Environment variable management |
| Nodemon | Auto-restart during development |
| CORS | Cross-Origin Resource Sharing middleware |

### DevTools & Deployment
| Tool | Purpose |
|---|---|
| Angular CLI (~13.3.5) | Project scaffolding, builds, dev server |
| Netlify | Frontend deployment |
| VS Code | Development environment |

---

## 🗂️ Project Structure

```
Juicy-N-Yummy/
├── Backend/                        # Node.js + Express REST API
│   ├── index.js                    # Server entry point
│   ├── package.json                # Backend dependencies
│   ├── .env                        # Environment variables (not committed)
│   ├── models/                     # Mongoose data models
│   │   ├── user.model.js           # User schema (auth)
│   │   ├── restaurant.model.js     # Restaurant schema
│   │   ├── menu.model.js           # Menu / food item schema
│   │   └── review.model.js         # Review/feedback schema
│   ├── routes/                     # Express route definitions
│   │   ├── auth.routes.js          # Register / Login routes
│   │   ├── restaurant.routes.js    # Restaurant CRUD routes
│   │   ├── menu.routes.js          # Menu item routes
│   │   └── review.routes.js        # Review routes
│   ├── controllers/                # Route handler logic
│   │   ├── auth.controller.js
│   │   ├── restaurant.controller.js
│   │   ├── menu.controller.js
│   │   └── review.controller.js
│   └── middleware/
│       └── auth.middleware.js      # JWT verification middleware
│
├── src/                            # Angular frontend source
│   ├── app/
│   │   ├── app.module.ts           # Root Angular module
│   │   ├── app-routing.module.ts   # App-level route config
│   │   ├── components/             # Reusable UI components
│   │   ├── pages/                  # Route-level page components
│   │   │   ├── home/               # Landing / home page
│   │   │   ├── dashboard/          # Admin/user dashboard
│   │   │   ├── restaurant-detail/  # Individual restaurant page
│   │   │   ├── login/              # Login page
│   │   │   └── register/           # Sign-up page
│   │   ├── service/                # Angular HTTP services
│   │   │   └── api.service.ts      # HTTP calls to backend (http://localhost:5000)
│   │   └── models/                 # TypeScript interfaces/models
│   ├── assets/                     # Static assets (images, icons)
│   └── environments/               # Angular environment configs
│
├── screenshots/                    # Project screenshots
├── angular.json                    # Angular workspace config
├── tailwind.config.js              # TailwindCSS configuration
├── package.json                    # Frontend dependencies
├── tsconfig.json                   # TypeScript configuration
└── README.md
```

---

## 🔌 Backend API Architecture

The backend is a **RESTful API** built with **Node.js + Express**, connected to **MongoDB** via **Mongoose**. It runs on port `5000` by default and is consumed by the Angular frontend via HTTP services.

### Server Entry Point (`Backend/index.js`)
- Initializes the Express app
- Connects to MongoDB using Mongoose and the `MONGO_URI` from `.env`
- Registers all route modules
- Applies CORS and JSON middleware
- Starts listening on `PORT` (default: 5000)

### Authentication (`/api/auth`)
| Method | Route | Description | Auth Required |
|--------|-------|-------------|:---:|
| POST | `/api/auth/register` | Register a new user | ❌ |
| POST | `/api/auth/login` | Login and receive JWT token | ❌ |

### Restaurants (`/api/restaurants`)
| Method | Route | Description | Auth Required |
|--------|-------|-------------|:---:|
| GET | `/api/restaurants` | Get all restaurants | ❌ |
| GET | `/api/restaurants/:id` | Get a single restaurant by ID | ❌ |
| POST | `/api/restaurants` | Add a new restaurant | ✅ |
| PUT | `/api/restaurants/:id` | Update restaurant details | ✅ |
| DELETE | `/api/restaurants/:id` | Delete a restaurant | ✅ |

### Menu Items (`/api/menu`)
| Method | Route | Description | Auth Required |
|--------|-------|-------------|:---:|
| GET | `/api/menu/:restaurantId` | Get menu for a restaurant | ❌ |
| POST | `/api/menu` | Add a new menu item | ✅ |
| PUT | `/api/menu/:id` | Update a menu item | ✅ |
| DELETE | `/api/menu/:id` | Delete a menu item | ✅ |

### Reviews (`/api/reviews`)
| Method | Route | Description | Auth Required |
|--------|-------|-------------|:---:|
| GET | `/api/reviews/:restaurantId` | Get reviews for a restaurant | ❌ |
| POST | `/api/reviews` | Submit a new review | ✅ |
| DELETE | `/api/reviews/:id` | Delete a review | ✅ |

### JWT Middleware
Protected routes require an `Authorization: Bearer <token>` header. The `auth.middleware.js` verifies the JWT using `JWT_SECRET` from `.env` and attaches the decoded user to `req.user`.

---

## 🖥️ Frontend Pages

| Page | Route | Description |
|------|-------|-------------|
| **Home** | `/` | Landing page with featured restaurants, hero section, and location-based discovery |
| **Restaurant Detail** | `/restaurant/:id` | Full restaurant info: menu, gallery, reviews, and rating |
| **Dashboard** | `/dashboard` | User/admin panel — manage listings, reviews, and analytics |
| **Login** | `/login` | User authentication page |
| **Register** | `/register` | New user sign-up page |

### Angular Services (`src/app/service/`)
- **ApiService** — Centralized HTTP service using `HttpClient` with RxJS Observables; all API base URLs point to `http://localhost:5000` (configurable per environment).

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** v14+ and **npm**
- **MongoDB** (local instance or MongoDB Atlas URI)
- **Angular CLI** v13

### 1. Clone the Repository

```bash
git clone https://github.com/prakhar-5447/Juicy-N-Yummy.git
cd Juicy-N-Yummy
```

### 2. Install Frontend Dependencies

```bash
npm install
```

### 3. Install Backend Dependencies

```bash
cd Backend
npm install
cd ..
```

### 4. Configure Environment Variables

Create a `.env` file inside the `Backend/` folder:

```env
MONGO_URI="your_mongodb_connection_string"
JWT_SECRET="your_jwt_secret_key"
PORT=5000
```

### 5. Configure Frontend API Endpoint

Open `src/app/service/` and ensure the base URL is set to:

```
http://localhost:5000
```

### 6. Run Both Servers (Split Terminal)

**Terminal 1 — Frontend (Angular):**
```bash
npm start
```
Runs at: `http://localhost:4200`

**Terminal 2 — Backend (Node.js):**
```bash
cd Backend
npx nodemon index.js
```
Runs at: `http://localhost:5000`

---

## 📸 Screenshots

View all screenshots [here](https://github.com/prakhar-5447/Juicy-N-Yummy/blob/master/screenshots).

---

## 📦 Build for Production

```bash
npm run build
```

Output is generated in the `dist/` folder. The frontend is deployed via **Netlify**.

---

## 📄 License

Distributed under the **AGPL-3.0 License**. See [LICENSE](./LICENSE) for full details.

---

## 👥 Team

| | Name | GitHub |
|---|---|---|
| <img src="https://avatars.githubusercontent.com/u/80202909?v=4" width="40" style="border-radius:50%"> | Prakhar Sahu | [@prakhar-5447](https://github.com/prakhar-5447) |
| <img src="https://avatars.githubusercontent.com/u/80022922?v=4" width="40" style="border-radius:50%"> | Pratham Sahu | [@pratham-0094](https://github.com/pratham-0094) |

---

> ⭐ If you found this project helpful, consider giving it a star on GitHub!
