# Setup routing (file-based)

1- Install dependency:

```bash
npm install react-router-dom
```

2- Add layout in src/routes/Layout.tsx:

```typescript
import { Outlet, ScrollRestoration } from "react-router-dom";
import { NavigationMenu } from "@/components/ui/navigation-menu";

export const Layout = () => {
  return (
    <div className="min-h-screen bg-background">
      <header className="border-b">
        <NavigationMenu />
      </header>
      <main className="container mx-auto p-8">
        <Outlet />
      </main>
      <ScrollRestoration />
    </div>
  );
};

```

3- Add router in src/routes/router.tsx:

```typescript

import { createBrowserRouter } from "react-router-dom";
import { NotFound, Home } from "@/pages";
import { Layout } from "./Layout";

const appRoutes = [{ path: "/", element: <Home />, labelKey: "home" }];

const router = createBrowserRouter(
  [
    {
      path: "/",
      element: <Layout />,
      children: [
        ...appRoutes
          .filter((route) => route.path !== "/")
          .map((route) => ({
            path: route.path.replace(/^\//, ""),
            element: route.element,
            index: route.path === "/",
          })),
        {
          index: true,
          element: appRoutes.find((r) => r.path === "/")?.element,
        },
      ],
    },
    {
      path: "*",
      element: <NotFound />,
    },
  ],
  {
    basename: import.meta.env.BASE_URL,
  },
);

export default router;

```

4- Move App.tsx to src/routes":
\*\* Don't forget to modify the App.tsx import in main.tsx.

```typescript
import { RouterProvider } from "react-router-dom";
import router from "./router";

function App() {
  return <RouterProvider router={router} />;
}

export default App;

```
