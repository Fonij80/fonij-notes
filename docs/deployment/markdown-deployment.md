# MkDocs

1- Install MkDocs locally:

```bash
pip install mkdocs mkdocs-material
```

\*\* verify the installation:

```bash
mkdocs --version
```

2- Add mkdocs.yml to root folder:

```yaml
site_name: Fonij Dev Notes
site_description: "Fonij developer cheatsheets & guides"
site_url: https://fonij80.github.io/fonij-dev-notes/
repo_url: https://github.com/fonij80/fonij-dev-notes/
edit_uri: edit/main/docs/

theme:
  name: material
  palette:
    - scheme: default
      primary: indigo
      toggle:
        icon: material/weather-sunny
        name: Switch to dark mode
    - scheme: slate
      primary: indigo
      toggle:
        icon: material/weather-night
        name: Switch to light mode
  font:
    text: Inter
    code: JetBrains Mono
  icon:
    logo: material/language-javascript
    favicon: material/language-javascript
  features:
    - content.code.copy
    - navigation.sections
    - navigation.indexes
    - navigation.expand
    - search.suggest
    - search.highlight
    - content.tabs

nav:
  - 🚀 Home: index.md
  - 🤖 AI: ai/ai.md
  - ⚡ Next.js: nextjs/nextjs.md
  - 🐍 Django:
      - Overview: django/index.md
      - Guide: django/django.md
      - Conventions:
          - Naming: django/conventions/naming.md
  - ⚛️ ReactJS:
      - Overview: reactjs/index.md
      - Guide:
          - React Guide: reactjs/guide/react-guide.md
      - Conventions:
          - Naming: reactjs/conventions/naming.md
      - Setups:
          - Project Setup: reactjs/setups/project-setup.md
          - Routing Setup: reactjs/setups/routing-setup.md
          - Theme Setup: reactjs/setups/theme-setup.md
          - Multilinguality: reactjs/setups/multilinguality-setup.md
          - Deploy Setup: reactjs/setups/deploy-setup.md
  - 🏗️ Software Engineering: softwareengineering/design-patterns.md

plugins:
  - search

markdown_extensions:
  - pymdownx.highlight:
      anchor_linenums: true
  - pymdownx.superfences
  - pymdownx.inlinehilite
  - pymdownx.snippets
  - pymdownx.tabbed:
      alternate_style: true
  - attr_list
```

3- Move all .md files to a docs/

4- Create docs/index.md for homepage

5- Run locally:

```bash
mkdocs serve
```

6- Deploy:

```bash
mkdocs gh-deploy
```
