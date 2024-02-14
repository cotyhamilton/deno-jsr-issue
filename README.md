# deno jsr issues

## reproduce

failing imports

```ts
import { DenoKVAdapter } from "jsr:@cotyhamilton/lucia-adapter-denokv@next"; // the bad one
import { DenoKVAdapter } from "jsr:@cotyhamilton/lucia-adapter-denokv@0";
import { DenoKVAdapter } from "jsr:@cotyhamilton/lucia-adapter-denokv@1";
import { DenoKVAdapter } from "jsr:@cotyhamilton/lucia-adapter-denokv@1.0.0-next.1";
```

```sh
deno run --unstable-kv issue.ts
#
# ============================================================
# Deno has panicked. This is a bug in Deno. Please report this
# at https://github.com/denoland/deno/issues/new.
# If you can reliably reproduce this panic, include the
# reproduction steps and re-run with the RUST_BACKTRACE=1 env
# var set and include the backtrace in your report.
#
# Platform: macos aarch64
# Version: 1.40.2
# Args: ["deno", "run", "--unstable-kv", "issue.ts"]
#
# thread 'main' panicked at /Users/runner/.cargo/registry/src/index.crates.io-6f17d22bba15001f/deno_semver-0.5.4/src/lib.rs:265:32:
# programming error: cannot use matches with a tag: next
# note: run with `RUST_BACKTRACE=1` environment variable to display a backtrace
#
```

## working

```sh
deno run --unstable-kv working.ts
```
