# lib-fetch-c

`fetch-c` — `fetch` backed by libcurl (codegen bindings): sync calls
plus `fetch_task`, a step-arrow for `concurrent-epoll`.

## Layout

| path | role |
| --- | --- |
| `src/index.hnl` | the backend module (`fetch-c`) |
| `src/fetch-c.test.hnl` | tests — spin up `scripts/test_server.py` for live cases |
| `scripts/test_server.py` | local HTTP test server used by the suite |
| `pkg.hnl` | manifest — deps `fetch`, `curl`, `libc` (`branch:main`) |
| `scripts/hnl-gate.sh` | `.hnl` gate |
| `workflows/gate.yaml` | CI — shared `handl-gates` campaign |

## Contract

- Implements the `lib-fetch` contract over `lib-curl`'s generated FFI
  bindings — no Rust crate, pure `.hnl` over `ffi.call`.
- `fetch_task` exposes the async shape for the concurrent scheduler.

## Verification

```bash
HNL=../host-cli/target/debug/hnl scripts/hnl-gate.sh
```

<!-- myco:agent-awareness -->

## Agent awareness

- Session start / any work discussion: run `myco status --prompt`
  before proposing next steps — know the board first.
- User describes new work → offer to capture it (`myco todo add`,
  `issue new`, `proposal new`). Don't wait to be asked.
- Picking up a task: `myco resume <ID>` is the briefing.
- Wrapping up: `myco handoff <ID>` anything resumable; keep statuses
  honest (claimed → in-progress → blocked/done).

<!-- /myco:agent-awareness -->
