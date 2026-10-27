# Contributing a Package

Thank you for adding to the GlowLang ecosystem! To publish a package:

1. **Fork** this repository and create a branch.
2. Create a directory `packages/<name>/` (lowercase, words joined with `_`).
3. Add the package source as **`packages/<name>/<name>.glow`**. This is the file `gdu install
   <name>` downloads; users load it with `use "<name>"`.
4. Add `packages/<name>/package.json` (format below).
5. Add `packages/<name>/README.md` with a short description and a usage example that runs.
6. Test it with the current GlowLang build:
   ```bash
   mkdir -p demo/.glow_pkg && cp packages/<name>/<name>.glow demo/.glow_pkg/
   # write demo/app.glow that does: use "<name>" ... and run it:
   glowlang run demo/app.glow
   ```
7. Commit with a sign-off (`git commit -s`, Developer Certificate of Origin) and open a pull
   request.

## `package.json`

```json
{
  "name": "your_package",
  "version": "1.0.0",
  "author": "Your Name",
  "repo": "https://github.com/anshumali19/GlowLang-packages",
  "entry": "your_package.glow",
  "description": "One sentence on what it does.",
  "license": "Apache-2.0 WITH Commons-Clause (see GlowLang-core LICENSE)"
}
```

`entry` is the file name inside the package directory. Versions use `MAJOR.MINOR.PATCH`.

## Guidelines

* Package functions and blueprints share the program's global namespace: prefix helper names
  (for example `json_merge`, not `merge`) so they do not replace other definitions.
* Use only functions that exist in GlowLang today; see the
  [language reference](https://github.com/anshumali19/GlowLang-core/blob/main/docs/language_reference.md).
* Describe what the package really does — no performance claims without a benchmark.

A maintainer will review the pull request. Once merged, `gdu install <name>` can fetch the
package.

By contributing you agree that your package is licensed under the GlowLang license (Apache 2.0
with the Commons Clause; see GlowLang-core's LICENSE), and you keep the copyright in your work.
