# Setup react.js project using vite ([step-by-step](https://ui.shadcn.com/docs/installation/vite))

1- Create project:

```bash
    npm create vite@latest
```

2- Install dependencies:

```bash
    npm install
    npm install -D @types/node
```

3- Add Tailwind:

```bash
    npm install -D tailwindcss @tailwindcss/vite
    npm install -D tailwindcss-rtl # for rtl websites
```

4- Replace the whole 'src/index.css' by:

```css
@import "tailwindcss";
```

\*\* You can remove App.css file and its import in App.tsx (not usable).

5- Replace the whole 'tsconfig.json' by:

```json
{
  "files": [],
  "references": [
    { "path": "./tsconfig.app.json" },
    { "path": "./tsconfig.node.json" }
  ],
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["./src/*"]
    }
  }
}
```

6- Add below line to "compilerOptions" in 'tsconfig.app.json' (for resolving path in your IDE):

```json
"baseUrl": ".",
    "paths": {
      "@/*": ["./src/*"]
    }
```

7- Replace the whole 'vite.config.ts' by:

```typescript
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
});
```

8- Add shadcn:

```bash
npx shadcn@latest init
```

\*\* Now you can add shadcn components by:

```bash
npx shadcn@latest add [component_name]
```

9- Run project:

```bash
npm run dev
```
