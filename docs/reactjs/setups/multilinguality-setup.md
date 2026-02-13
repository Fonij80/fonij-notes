# Setup multilinguality

1- Install dependency:

```bash
npm install i18next react-i18next i18next-http-backend i18next-browser-languagedetector
```

2- Add json files to src/locales/[lang]/[file_name].json

3- Add i18n.ts to src:

```typescript
import i18n from "i18next";
import { initReactI18next } from "react-i18next";
import HttpBackend from "i18next-http-backend";
import LanguageDetector from "i18next-browser-languagedetector";

void i18n
  .use(HttpBackend)
  .use(LanguageDetector)
  .use(initReactI18next)
  .init({
    fallbackLng: "en",
    supportedLngs: ["en", "fa"],
    ns: ["file_name"],
    defaultNS: "file_name",
    debug: import.meta.env.DEV,

    backend: {
      loadPath: "/locales/{{lng}}/{{ns}}.json",
    },

    detection: {
      order: ["querystring", "localStorage", "navigator", "htmlTag"],
      caches: ["localStorage"],
    },

    interpolation: {
      escapeValue: false,
    },

    react: {
      useSuspense: true,
    },
  });

export default i18n;
```

4- Add below line to main.tsx:

```typescript
import "./i18n";
```

\*\* use this library in your component:

```typescript
import { useTranslation } from 'react-i18next';
function App() {
  const { t } = useTranslation(['common', 'dashboard']);

  return (
    <div>
      <h1>{t('title')}</h1>
      <p>{t('subtitle')}</p>
    </div>
  );
}

```

- you can also add a LanguageSwitcher.tsx component:

```typescript
import { useTranslation } from 'react-i18next';

const languages = [
  { code: 'en', label: 'English' },
  { code: 'fa', label: 'فارسی' }
];

export function LanguageSwitcher() {
  const { i18n } = useTranslation();

  const handleChange = (e: React.ChangeEvent<HTMLSelectElement>) => {
    void i18n.changeLanguage(e.target.value);
  };

  return (
    <select value={i18n.resolvedLanguage} onChange={handleChange}>
      {languages.map((lng) => (
        <option key={lng.code} value={lng.code}>
          {lng.label}
        </option>
      ))}
    </select>
  );
}

```
