# Local work on top of upstream

This fork (`eejd/rs-rtk`) mirrors `rtk-ai/rtk` on `develop` (never edited). The `local` branch is a
release base plus the work below; port `rtk-local` in `eejd/macports-ports-local` builds the tags
`v<base>-local<NN>`.

| Change | Origin | Upstream status |
|---|---|---|
| Claude `PreToolUse` hook asserts `permissionDecision: "allow"` with `updatedInput` for Ask/Default verdicts too (Claude rejects `updatedInput` without it) | local (formerly `patch-claude-pretooluse-allow.diff` in `macports-ports-local`), re-applied by hand on v1.0.1 | not submitted; upstream v1.0.1 omits the field for Ask/Default on purpose (#3037 context) |
| Built-in filters `port`, `colima`, `launchctl`, `zerotier-cli` (`src/filters/*.toml`; builtin-filter count test = 66) | local, eejd/rs-rtk#14-#17 | not submitted |
| `rust-version` MSRV commit (`ea2e1bea`, eejd/rs-rtk#4) | local | dropped on v1.0.1: upstream carries `rust-version = "1.91"` itself |
