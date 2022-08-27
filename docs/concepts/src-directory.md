---
description: |
  Put your code in a directory of your choosing (i.e. src, app, etc.)
---

If you'd like your code to live in a `src` or any other directory you'll need
to move your `import_map.json`, `dev.ts`, `main.ts`, `routes/`, `islands/`,
and `static/` files/directories into the prefered directory. Your
directory/file structure should end up looking like something below:

```
.
├── deno.json
├── src/
│   ├── islands/
│   │   ├── Counter.tsx
│   │   └── ...
│   ├── routes/
│   │   ├── index.tsx
│   │   └── ...
│   ├── static/
│   │   └── ...
│   ├── dev.ts
│   ├── import_map.json
│   ├── main.ts
│   └── ...
└── ...
```

You will also need to update your `deno.json` with the new entrypoint and
import map location like so:

```json
{
  "tasks": {
    "start": "deno run -A --watch=src/static/,src/routes/ src/dev.ts"
  },
  "importMap": "./src/import_map.json"
}
```
