# 🚀 JobFinder

A modern, full-featured job search and management application built with Angular 21. JobFinder helps users discover job opportunities, save favorites, track applications, and manage their career journey in one place.

![Angular](https://img.shields.io/badge/Angular-21.0.0-red?style=flat&logo=angular)
![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue?style=flat&logo=typescript)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-4.1-38B2AC?style=flat&logo=tailwind-css)
![NgRx](https://img.shields.io/badge/NgRx-21.0.1-purple?style=flat&logo=ngrx)

## ✨ Features

### 🔐 Authentication & User Management
- **User Registration & Login** - Secure authentication system
- **Remember Me** - Option to persist session in localStorage or sessionStorage
- **Profile Management** - Update user information
- **Session Management** - Automatic session handling with guards

### 💼 Job Discovery
- **Job Listings** - Browse jobs from The Muse API
- **Job Details** - View comprehensive job information with resolver pre-loading
- **Search & Filter** - Find jobs that match your criteria
- **Responsive Design** - Optimized for desktop, tablet, and mobile devices

### ⭐ Favorites Management
- **Add to Favorites** - Save interesting job opportunities
- **Favorites Dashboard** - View all your saved jobs in one place
- **NgRx State Management** - Efficient state handling with Redux pattern
- **Persistent Storage** - Favorites synced with backend

### 📋 Job Tracking (Suivi)
- **My Jobs Dashboard** - Track your job applications
- **Application Status** - Monitor the progress of your applications
- **Centralized Management** - Organize all your job prospects

### 🎨 UI/UX
- **Modern Design** - Beautiful interface with Tailwind CSS v4
- **Toast Notifications** - User feedback with ngx-sonner
- **Loading States** - Smooth loading experience with ngx-spinner and HTTP interceptors
- **Smooth Animations** - Polished user interactions

## 🛠️ Tech Stack

### Frontend
- **Framework**: Angular 21.0.0
- **State Management**: NgRx Store 21.0.1 (Effects, Store, DevTools)
- **Styling**: Tailwind CSS 4.1.12
- **HTTP Client**: Angular HttpClient with interceptors
- **Routing**: Angular Router with lazy loading
- **Forms**: Reactive Forms with validation
- **Notifications**: ngx-sonner 3.1.0
- **Loading Indicators**: ngx-spinner 21.0.0

### Backend (Mock)
- **API Server**: JSON Server 1.0.0-beta.5
- **External API**: The Muse Public API
- **Storage**: localStorage & sessionStorage

## 📁 Project Structure

```
job-finder/
├── src/
│   ├── app/
│   │   ├── core/                      # Core module
│   │   │   ├── db/                    # Mock database (db.json)
│   │   │   ├── guards/                # Route guards
│   │   │   ├── interceptors/          # HTTP interceptors
│   │   │   │   └── loading.interceptor.ts
│   │   │   ├── models/                # TypeScript interfaces
│   │   │   │   ├── favorite.model.ts
│   │   │   │   ├── job.model.ts
│   │   │   │   ├── job-resp.model.ts
│   │   │   │   ├── login.model.ts
│   │   │   │   ├── suivi.model.ts
│   │   │   │   ├── user.model.ts
│   │   │   │   └── user-response.model.ts
│   │   │   ├── resolvers/             # Route resolvers
│   │   │   │   └── job.resolver.ts
│   │   │   ├── services/              # Business logic services
│   │   │   │   ├── favorites.service.ts
│   │   │   │   ├── jobs.service.ts
│   │   │   │   ├── suivi.service.ts
│   │   │   │   └── users.service.ts
│   │   │   └── store/                 # NgRx state management
│   │   │       └── favorites/
│   │   │           ├── favorite.actions.ts
│   │   │           ├── favorite.effects.ts
│   │   │           ├── favorite.reducer.ts
│   │   │           └── favorite.selectors.ts
│   │   ├── features/                  # Feature modules
│   │   │   ├── auth/                  # Authentication
│   │   │   │   ├── login/
│   │   │   │   └── signup/
│   │   │   ├── favorites/             # Favorites management
│   │   │   │   └── favorites-page/
│   │   │   ├── jobs/                  # Job discovery
│   │   │   │   ├── job-detail/
│   │   │   │   └── jobs-page/
│   │   │   ├── my-jobs/               # Job tracking
│   │   │   │   └── my-jobs-page/
│   │   │   ├── profile/               # User profile
│   │   │   └── pages/                 # Other pages
│   │   ├── shared/                    # Shared components
│   │   │   └── components/
│   │   │       ├── job-card/
│   │   │       ├── my-job-card/
│   │   │       └── navbar/
│   │   ├── app.config.ts              # App configuration
│   │   ├── app.routes.ts              # Route definitions
│   │   └── app.ts                     # Root component
│   ├── env/
│   │   └── env-variables.ts           # Environment variables
│   ├── index.html
│   ├── main.ts
│   └── styles.css
├── public/                            # Static assets
├── angular.json                       # Angular configuration
├── package.json
├── tsconfig.json
└── README.md
```

## 🚀 Getting Started

### Prerequisites

- **Node.js**: >= 18.x
- **npm**: >= 10.x
- **Angular CLI**: 21.0.4

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd job-finder
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start the JSON Server (Backend)**
   ```bash
   npm run jsonServer
   ```
   The mock API will run on `http://localhost:3000`

4. **Start the development server**
   ```bash
   npm start
   ```
   or
   ```bash
   ng serve
   ```
   Navigate to `http://localhost:4200/`

The application will automatically reload when you change source files.

## 📝 Available Scripts

| Command | Description |
|---------|-------------|
| `npm start` | Start development server on http://localhost:4200 |
| `npm run jsonServer` | Start JSON Server on http://localhost:3000 |
| `npm run build` | Build the project for production |
| `npm run watch` | Build in watch mode |
| `npm test` | Run unit tests with Vitest |

## 🔑 API Endpoints

### Local JSON Server (http://localhost:3000)

- `GET /users` - Get all users
- `POST /users` - Register new user
- `PUT /users/:id` - Update user
- `GET /favorits` - Get all favorites
- `POST /favorits` - Add favorite
- `DELETE /favorits/:id` - Remove favorite
- `GET /suivis` - Get all job trackings
- `POST /suivis` - Add job tracking
- `PUT /suivis/:id` - Update job tracking

### External API

- **The Muse API**: `https://www.themuse.com/api/public`
  - Used for fetching real job listings

## 🎯 Key Features Implementation

### NgRx State Management
The application uses NgRx for managing favorites state with actions, effects, reducers, and selectors for predictable state updates.

### HTTP Interceptors
Loading interceptor automatically shows/hides loading spinner for all HTTP requests.

### Route Guards
Authentication guards protect routes that require user login.

### Route Resolvers
Job resolver pre-fetches job data before navigating to job detail page for better UX.

### Lazy Loading
All feature modules are lazy-loaded for optimal performance and faster initial load time.

### Remember Me Feature
User sessions can be persisted in:
- **localStorage** - When "Remember Me" is checked (persists across browser sessions)
- **sessionStorage** - When unchecked (only persists for current session)

## 🎨 Styling

The application uses **Tailwind CSS v4** with a custom design system:
- Custom color palette with emerald accent
- Responsive breakpoints
- Modern glass-morphism effects
- Smooth transitions and animations

## 🧪 Testing

Run unit tests:
```bash
npm test
```

The project uses Vitest for testing Angular components and services.

## 📦 Building for Production

Build the project:
```bash
npm run build
```

The build artifacts will be stored in the `dist/` directory, optimized for production deployment.

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b features/amazing-feature`)
3. Commit your changes (`git commit -m 'feat: add amazing feature'`)
4. Push to the branch (`git push origin features/amazing-feature`)
5. Open a Pull Request

### Commit Convention
This project follows conventional commits:
- `feat:` - New features
- `fix:` - Bug fixes
- `chore:` - Maintenance tasks
- `refactor:` - Code refactoring
- `docs:` - Documentation updates

## 📄 License

This project is private and proprietary.

## 👨‍💻 Author

**Yacine MARZOUK**

## 🙏 Acknowledgments

- [Angular](https://angular.dev) - The web framework
- [The Muse API](https://www.themuse.com/developers/api/v2) - Job listings data
- [Tailwind CSS](https://tailwindcss.com) - Utility-first CSS framework
- [NgRx](https://ngrx.io) - State management
- [JSON Server](https://github.com/typicode/json-server) - Mock REST API

---

Built with ❤️ using Angular 21
