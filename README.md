# lib-fetch-c

`fetch` backed by libcurl (sdkgen bindings) — sync plus `fetch_task` step-arrow for `concurrent-epoll`.

## Layout

```text
src/                     the .hnl sources
pkg.hnl                  package manifest
scripts/hnl-gate.sh      the gate
ci.sh                    bupha entry
```

## Gate

```bash
HNL=../host-cli/target/debug/hnl scripts/hnl-gate.sh
```

## License

MIT.
