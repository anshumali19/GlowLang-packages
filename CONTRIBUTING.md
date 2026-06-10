# Contributing a Package

To add a new package to the GlowLang Ecosystem:

1. Fork this repository.
2. Create a new directory under `packages/` with your package name.
3. Add a `package.json` with your package metadata.
4. Add a `README.md` explaining how to use it.
5. Open a Pull Request!

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
