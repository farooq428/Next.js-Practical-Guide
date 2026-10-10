# Next.js Practical Guide

A step-by-step practical guide to learning Next.js, from basic setup to building, testing, and deploying production-ready applications.

## 📚 Table of Contents

1. [Introduction to Next.js](#1-introduction-to-nextjs)
2. [Prerequisites](#2-prerequisites)
3. [Create a Next.js App](#3-create-a-nextjs-app)
4. [Project Structure](#4-project-structure)
5. [Run the Development Server](#5-run-the-development-server)
6. [Create Your First Page](#6-create-your-first-page)
7. [Routing](#7-routing)
8. [Components](#8-components)
9. [Styling](#9-styling)
10. [Build and Production](#10-build-and-production)
11. [Useful Commands](#11-useful-commands)

---

## 1. Introduction to Next.js

Next.js is a React framework used to build modern web applications.

**Key features:**
- File-based routing
- Server-side rendering (SSR)
- Static site generation (SSG)
- React Server Components
- API endpoints and backend logic
- Image and font optimization
- Production build optimization

## 2. Prerequisites

Before starting, make sure you have:

- Node.js installed
- npm installed
- VS Code installed
- Basic knowledge of JavaScript and React

Check your installed versions:

```bash
node -v
npm -v
```

## 3. Create a Next.js App

### Option 1: Create a New Folder

Run the following command in the VS Code terminal:

```bash
npx create-next-app@latest my-next-app
```

Move into the project folder:

```bash
cd my-next-app
```

### Option 2: Create an App in the Current Folder

If you have already opened your project folder in VS Code, run:

```bash
npx create-next-app@latest .
```

**Note:** The dot (`.`) means the current directory. Use this command in an empty folder or after checking that existing files will not conflict with the setup.

### Recommended Setup

- TypeScript: Yes
- ESLint: Yes
- Tailwind CSS: Yes
- `src/` directory: No
- App Router: Yes
- Import alias: Default (`@/*`)

Choose the available options that match your project requirements.

## 4. Project Structure

A basic Next.js project using the App Router:

```text
my-next-app/
├── app/
│   ├── favicon.ico
│   ├── globals.css
│   ├── layout.tsx
│   └── page.tsx
├── components/
├── public/
├── .gitignore
├── next.config.ts
├── package.json
├── tsconfig.json
└── README.md
```

**Important files:**

- `app/page.tsx` — homepage.
- `app/layout.tsx` — root layout shared across pages.
- `app/globals.css` — global styles.
- `components/` — reusable UI components.
- `public/` — static assets such as images and icons.
- `next.config.ts` — Next.js configuration.
- `package.json` — dependencies and npm scripts.
- `tsconfig.json` — TypeScript configuration.

The `components/` folder can be placed at the project root or inside `app/`. Choose a consistent structure based on your application.

## 5. Run the Development Server

Start the development server:

```bash
npm run dev
```

Open your browser:

```text
http://localhost:3000
```

The server usually updates the browser automatically when you save changes.

Stop the server using:

```text
Ctrl + C
```

## 6. Create Your First Page

Open `app/page.tsx` and replace its contents with:

```tsx
export default function Home() {
  return (
    <main>
      <h1>My First Next.js App</h1>
      <p>Learning Next.js step by step.</p>
    </main>
  );
}
```

**Explanation:**

- `Home` is a React component.
- `return` defines the UI.
- JSX describes the HTML-like structure.
- `export default` makes the component available to Next.js as the page.
- `app/page.tsx` represents the `/` route.

## 7. Routing

Next.js uses folders and files to define routes through the App Router.

### Create the About Page

Create this file:

```text
app/about/page.tsx
```

Add the following code:

```tsx
export default function About() {
  return (
    <main>
      <h1>About Us</h1>
      <p>This is the About page.</p>
    </main>
  );
}
```

Visit:

```text
http://localhost:3000/about
```

### Routing Examples

| File | URL |
|---|---|
| `app/page.tsx` | `/` |
| `app/about/page.tsx` | `/about` |
| `app/contact/page.tsx` | `/contact` |
| `app/products/page.tsx` | `/products` |

## 8. Components

Components help you reuse UI code across multiple pages.

Create `components/Header.tsx`:

```tsx
export default function Header() {
  return (
    <header>
      <h1>My Website</h1>
    </header>
  );
}
```

Use it in `app/page.tsx`:

```tsx
import Header from "@/components/Header";

export default function Home() {
  return (
    <main>
      <Header />
      <p>Welcome to my website.</p>
    </main>
  );
}
```

**Note:** The `@/` alias normally points to the project root when the default import alias is configured and there is no `src/` directory.

## 9. Styling

### Global CSS

Write global styles in `app/globals.css`.

```css
body {
  margin: 0;
  font-family: Arial, sans-serif;
}

main {
  padding: 24px;
}
```

### Tailwind CSS

If Tailwind CSS is enabled, you can style elements directly using utility classes:

```tsx
export default function Home() {
  return (
    <main className="min-h-screen bg-gray-100 p-8">
      <h1 className="text-3xl font-bold text-blue-600">
        My Next.js App
      </h1>
      <p className="mt-4 text-gray-700">
        Learning Tailwind CSS.
      </p>
    </main>
  );
}
```

## 10. Build and Production

### Step 1: Run ESLint

```bash
npm run lint
```

Use the lint command configured in your `package.json` to check for code issues.

### Step 2: Create a Production Build

```bash
npm run build
```

This checks and prepares your application for production.

### Step 3: Start the Production Server

```bash
npm run start
```

Run this after a successful build. The `start` script normally serves the production build.

### Step 4: Deployment

A typical deployment workflow is:

```text
Developer
    ↓
Git and GitHub
    ↓
GitHub Actions (CI)
    ↓
Lint and Build
    ↓
Docker Image
    ↓
Container Registry
    ↓
Cloud VPS
    ↓
Docker Compose
    ↓
Nginx + HTTPS
    ↓
Live Website
```

The exact workflow depends on your hosting provider and deployment approach.

## 11. Useful Commands

| Command | Purpose |
|---|---|
| `node -v` | Check Node.js version |
| `npm -v` | Check npm version |
| `npx create-next-app@latest .` | Create an app in the current folder |
| `npm install` | Install project dependencies |
| `npm run dev` | Start development server |
| `npm run lint` | Check code with ESLint |
| `npm run build` | Create production build |
| `npm run start` | Start production server |
| `npm install package-name` | Install a package |

---

## 🎯 Practical Learning Roadmap

Follow these topics in order:

- [ ] Install Node.js and create a Next.js app.
- [ ] Understand the App Router and project structure.
- [ ] Create pages and reusable components.
- [ ] Learn layouts and nested routes.
- [ ] Learn Client Components and Server Components.
- [ ] Use props, state, and event handlers.
- [ ] Build forms and handle user input.
- [ ] Fetch data from APIs.
- [ ] Create Route Handlers and connect a database.
- [ ] Learn loading, error, and not-found pages.
- [ ] Add authentication and environment variables.
- [ ] Optimize images, metadata, and SEO.
- [ ] Run lint checks and production builds.
- [ ] Configure GitHub Actions for CI/CD.
- [ ] Dockerize and deploy the application.

## Conclusion

Practice each topic by building small projects. Once you understand the basics, build a complete application using Next.js, TypeScript, Tailwind CSS, API integration, and a professional deployment workflow.

**Goal:** Build, test, and deploy production-ready Next.js applications.
