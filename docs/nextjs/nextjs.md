# Next.js project setup (step-by-step)

1- create project:

```bash
  npx create-next-app@latest your-app-name
```

# Multilingual Website

$ npm install next-intl

- Folders' structure:
  src/
  app/
  [locale]/
  layout.tsx
  page.tsx
  i18n/
  routing.ts
  request.ts
  messages/
  en.json
  fa.json

- next.config.ts:

  import type { NextConfig } from "next";
  import createNextIntlPlugin from "next-intl/plugin";

  const withNextIntl = createNextIntlPlugin("./app/i18n/request.ts");

  const nextConfig: NextConfig = {
  typescript: {
  ignoreBuildErrors: true,
  },
  };

  export default withNextIntl(nextConfig);

- routing.ts (single source of truth for locales):

  import { defineRouting } from "next-intl/routing";

  export const routing = defineRouting({
  locales: ["en", "fa"],
  defaultLocale: "en",
  });

- request.ts:

  import { getRequestConfig } from "next-intl/server";
  import { hasLocale } from "next-intl";
  import { routing } from "./routing";

  export default getRequestConfig(async ({ requestLocale }) => {
  const requested = await requestLocale;

        const locale = hasLocale(routing.locales, requested)
            ? requested
            : routing.defaultLocale;

        const messages = (await import(`../messages/${locale}.json`)).default;

        return {
            locale,
            messages,
        };

  });

- wrap layout.tsx in nextintl provider

  import type { Metadata } from "next";
  import { NextIntlClientProvider, hasLocale } from "next-intl";
  import { notFound } from "next/navigation";
  import { routing } from "../i18n/routing";
  import getRequestConfig from "../i18n/request";

  export const metadata: Metadata = {
  title: "Foroozan Iraji",
  description: "Fonij Portfolio",
  };

  type LayoutProps = {
  children: React.ReactNode;
  params: Promise<{ locale: string }>;
  };

  export default async function RootLayout({ children, params }: LayoutProps) {
  const { locale } = await params;

  // invalid locale
  if (!hasLocale(routing.locales, locale)) {
  notFound();
  }

  const requestConfig = await getRequestConfig({
  requestLocale: Promise.resolve(locale),
  });

  return (
  <html lang={locale}>
  <body>
  <NextIntlClientProvider
            locale={requestConfig.locale}
            messages={requestConfig.messages}
            >
  {children}
  </NextIntlClientProvider>
  </body>
  </html>
  );
  }

- proxy.ts (next.js v >= 16) or middleware.ts (next.js < 16>)

  import { routing } from "./app/i18n/routing";
  import createMiddleware from "next-intl/middleware";

  export const config = {
  matcher: ["/((?!api|_next|.*\\..*).*)"],
  };

  export default createMiddleware(routing);

# Shadcn

- install shadcn: $ npx shadcn@latest init
- install component: $ npx shadcn@latest add [component-name]
- button: $ npx shadcn@latest add button
- card: $ npx shadcn@latest add card

# Next.js Cheat Sheet

- create project:
  ```bash
    npx create-next-app@latest your-app-name
  ```
- multi-lingual lib:
  ```bash
    npm install next-intl
  ```
