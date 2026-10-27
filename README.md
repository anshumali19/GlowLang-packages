# GlowLang Packages

The public package registry for [GlowLang](https://github.com/anshumali19/GlowLang-core). Every
package here can be installed with `gdu`, the Glow Dependency Utility, which also lives in this
repository (`gdu/`).

## Packages

| Package | What it provides |
|---------|------------------|
| [`ai`](packages/ai) | Neural networks: `Layer`, `NeuralNet`, losses, optimizers, a training loop |
| [`database`](packages/database) | `Database` class over the built-in SQLite module |
| [`dataset`](packages/dataset) | Load, split, shuffle, batch and transform datasets |
| [`db`](packages/db) | Minimal SQLite `Model` helper |
| [`http`](packages/http) | HTTP client: `HttpClient`, `http_get`, `http_post`, `http_post_json` |
| [`json`](packages/json) | JSON path queries, schema validation, diff, merge, pretty-printing |
| [`middleware`](packages/middleware) | Middleware pipeline for HTTP requests and responses |
| [`ml_pipeline`](packages/ml_pipeline) | Machine-learning pipeline steps |
| [`natural`](packages/natural) | Natural-language helpers: `keep`, `apply`, `even`, `avg`, `root`, `dist` |
| [`tensor`](packages/tensor) | Tensor creation, statistics, activations and matrix helpers |
| [`web`](packages/web) | Web framework: router, middleware, JSON responses |

## Using a package

```bash
gdu install json
```

`gdu` saves the package as `.glow_pkg/json.glow` in your project and records it in `Glow.deps`.
Then load it by name:

```glow
use "json"

let data = json.parse('{"user": {"name": "Ada"}}')
show jpath(data).get("user.name")
```

`use "name"` looks for `name.glow` next to your program first, then for an installed package in
`.glow_pkg/`, then in GlowLang's bundled `lib/` folder.

## Installing GlowLang and `gdu`

### Option 1: pre-built binaries

Download an archive for Windows, Linux or macOS (x64) from the
**[Releases page](https://github.com/anshumali19/GlowLang-packages/releases)**, or let `gdu`
download the latest release and add it to your PATH:

```bash
gdu install glowlang
```

The published releases can lag behind the source in
[GlowLang-core](https://github.com/anshumali19/GlowLang-core). For the newest fixes, build from
source (option 2).

### Option 2: build from source

```bash
git clone https://github.com/anshumali19/GlowLang-core.git
cd GlowLang-core
make                  # Linux/macOS: builds bin/glowlang and bin/gdu
.\build.bat           # Windows (Visual Studio Build Tools + vcpkg; see the core README)
```

### Building only `gdu`

```bash
cd GlowLang-packages/gdu
# Debian/Ubuntu prerequisites: sudo apt-get install -y gcc libsqlite3-dev libssl-dev
gcc gdu.c -o gdu -O2 -lsqlite3 -lcrypto     # or simply: make
```

## Contributing a package

See the [package contributor guide](CONTRIBUTING.md). `gdu/package_lint.glow` checks a package's
layout before you open a pull request.

## License

Packages are released under the GlowLang license (Apache License 2.0 with the Commons Clause) —
see [LICENSE in GlowLang-core](https://github.com/anshumali19/GlowLang-core/blob/main/LICENSE).
Programs you write with these packages are yours.
