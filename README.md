# juice-shop-scan-target

Static-analysis input for a SAST tool benchmark. This repository contains a **modified subset** of
[OWASP Juice Shop](https://github.com/juice-shop/juice-shop), an intentionally insecure web application.

> **Do not deploy or run this code.** It is deliberately vulnerable and is published only as a fixed input for
> static analysis tools.

## Source

| | |
|---|---|
| Upstream | https://github.com/juice-shop/juice-shop |
| Release | `v20.3.0` |
| Commit | `f189f521266f42c6bd05884468292000cee852ed` |
| License | MIT, see [LICENSE](LICENSE) (copyright Bjoern Kimminich & the OWASP Juice Shop contributors) |

## Modifications

1. **Subset of files (290)**: application TypeScript and Angular HTML under `server.ts`, `app.ts`, `routes/`, `lib/`,
   `models/`, `data/*.ts` and `frontend/src/`, plus the `package.json` and `tsconfig` files needed for analysis.
   Tests, static data, assets, translations, infrastructure files, and the CTF training and scoring components of
   Juice Shop are not included.
2. **Comments removed**: Juice Shop's internal `// vuln-code-snippet ...` annotation comments were removed. Lines
   that held only such a comment are kept as empty lines, so every remaining line has the same line number as in
   the upstream commit.

No other code was changed.

## Integrity

`SCAN-INPUT.sha256` lists the SHA-256 of every analysed file (paths relative to the repository root, excluding this
README, `LICENSE` and the manifest itself). Verify with:

```bash
shasum -a 256 -c --quiet SCAN-INPUT.sha256
```

The tag `scope-v2` marks the exact input used by the benchmark.
