# Github pages

1- Install Github Pages:

```bash
npm install --save-dev gh-pages
```

2- Update package.json:

```json
{
  "name": "PROJECT_NAME",
  "homepage": "https://YOUR_USERNAME.github.io/REPO_NAME",
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview",
    "predeploy": "npm run build",
    "deploy": "gh-pages -d dist"
  }
}
```

3- Configure vite.config.ts

```ts
import path from "path";
import tailwindcss from "@tailwindcss/vite";
import react from "@vitejs/plugin-react";
import { defineConfig } from "vite";

// https://vite.dev/config/
export default defineConfig({
  plugins: [react(), tailwindcss()],
  resolve: {
    alias: {
      "@": path.resolve(__dirname, "./src"),
    },
  },
  base: "/REPO_NAME/",
});
```

4- Test locally:

```bash
npm run build
npm run preview
```

\*\* 'npm run dev' vs 'npm run preview'

| Feature     | npm run dev (vite)                      | npm run preview (vite preview)      |
| ----------- | --------------------------------------- | ----------------------------------- |
| Purpose     | Development - code editing + hot reload | Production testing - test built app |
| Serves      | Source code (src/)                      | Built files (dist/)                 |
| Hot Reload  | ✅ Instant (HMR)                        | ❌ None                             |
| Speed       | Fastest (no build)                      | Production optimized                |
| Port        | 5173                                    | 4173                                |
| When to use | Daily coding                            | Before deploy                       |

5- Deploy

```bash
npm run deploy
```

\*\* Must add public/404.html so github doesn't server its own 404:

- Without 404.html: GitHub serves its own 404 page → Game over
- With 404.html: GitHub serves your index.html → React Router takes over

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" type="image/svg+xml" href="/vite.svg" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Fonij React Template</title>
  </head>
  <body>
    <div id="root"></div>
    <!-- 👈 NO <script src="/src/main.tsx"> - This breaks production! -->
    <script type="module" src="/assets/index-[HASH].js"></script>
    <!-- Vite replaces [HASH] with actual filename during build -->
  </body>
</html>
```
