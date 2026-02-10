# Learn React

## Setup Tailwind Shadcn project

1. `npm create vite@latest `
2. `npm install tailwindcss @tailwindcss/vite`
3. `npm install -D @types/node`
4. For Right to Left website: `npm install -D tailwindcss-rtl`
5. Remove all styles in index.css and add: `@import "tailwindcss";`

- you can remove App.css file and its import in App.tsx

6. Edit tsconfig.json:
<pre>
"compilerOptions": {
  "baseUrl": ".",
  "paths": {
    "@/*": ["./src/*"]
  }
}
</pre>

7. Edit tsconfig.app.json:
<pre>
"compilerOptions": {
  // ...
  "baseUrl": ".",
  "paths": {
    "@/*": [
      "./src/*"
    ]
  }
  // ...
}
</pre>

8. Update vite.config.ts:
<pre>
import path from "path"
import tailwindcss from "@tailwindcss/vite"
import react from "@vitejs/plugin-react"
import { defineConfig } from "vite"

// https://vite.dev/config/
export default defineConfig({
plugins: [react(), tailwindcss()],
resolve: {
alias: {
"@": path.resolve(\_\_dirname, "./src"),
},
},
})

</pre>

9. Install ShadCN: `npx shadcn@latest init`
10. Add components: `npx shadcn@latest add button`
11. Run project: `npm run dev`
