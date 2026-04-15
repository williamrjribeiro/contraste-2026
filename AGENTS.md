# Agents

## Cursor Cloud specific instructions

This is an early-stage TypeScript project using **Bun** as the runtime and package manager (`bun.lock`).

### Key commands

| Task            | Command                                               |
| --------------- | ----------------------------------------------------- |
| Install deps    | `bun install`                                         |
| Lint markdown   | `bun run lint:md`                                     |
| Format markdown | `bun run format:md`                                   |
| Run a `.ts` file | `bun run <file>.ts`                                  |
| Type-check      | `npx tsc --noEmit` (no `.ts` source files exist yet) |

### Notes

- There is no application server, database, or frontend — the project is in bootstrap stage.
- The sole runtime dependency is `csv-simple-parser` for CSV parsing.
- Bun must be on `$PATH`; it is installed to `~/.bun/bin`. If `bun` is not found, run `curl -fsSL https://bun.sh/install | bash`.
- Markdown lint/format uses `remark-cli` with GFM and preset lint rules configured in `package.json` under `remarkConfig`.
