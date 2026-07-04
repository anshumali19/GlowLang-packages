# Contributing a Package

To add a new package to the GlowLang Ecosystem:

1. Fork this repository.
2. Create a new directory under `packages/` with your package name.
3. Add your package source as `<name>.glow` (e.g. `packages/http/http.glow`).
   **This is the file `gdu` actually fetches** — a package without it installs
   only as a non-functional stub.
4. Add a `package.json` with your package metadata.
5. Add a `README.md` explaining how to use it.
6. Open a Pull Request!

## `package.json` format:

```json
{
  "name": "your-package",
  "version": "1.0.0",
  "author": "Your Name",
  "repo": "https://github.com/yourname/your-package",
  "entry": "main.glow",
  "description": "A brief description of what it does."
}
```

A maintainer will review your code. If approved and merged, `gdu` will automatically be able to fetch your package.
