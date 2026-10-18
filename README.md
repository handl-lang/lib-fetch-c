# lib-fetch-c

`fetch` backed by libcurl (sdkgen bindings) — sync plus `fetch_task` step-arrow for `concurrent-epoll`.

Part of the `handl-lang` org split (ADR-0128). History is a `git subtree
split` of the platform monorepo's `fetch-c/` (via `c`).

## Layout

```text
src/        the .hnl sources
pkg.hnl     dependencies, when any: `{ deps: { <name>: "branch:<ref>" } }`
```

## Gate

```bash
HNL=../host-cli/target/debug/hnl scripts/hnl-gate.sh
```
