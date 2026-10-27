# http

An HTTP client for GlowLang: GET, POST, PUT and DELETE requests with headers and timeouts,
built on the runtime's `http.request`. (To *serve* HTTP, use the built-in `http.listen`,
`http.accept`, `http.read` and `http.send` — see the
[HTTP server example](https://github.com/anshumali19/GlowLang-examples/tree/main/http_server).)

## Installation

```bash
gdu install http
```

## Usage

```glow
use "http"

let client = HttpClient()
client.set_header("Accept", "text/plain")
let response = client.get("http://localhost:8080/hello")

if response.ok:
    show response.status, response.body
else:
    show "Request failed:", response.status, response.error
end

# One-line helpers
let page = http_get("http://localhost:8080/")
let created = http_post_json("http://localhost:8080/items", {"name": "lamp"})
```

A response has `status`, `body`, `headers`, `ok` (status 200–299) and `error` (set when the
request could not be made).
