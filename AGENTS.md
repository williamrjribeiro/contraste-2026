# Agents

## Cursor Cloud specific instructions

This is an early-stage TypeScript project that uses **Bun** for the runtime, package manager (`bun.lock`), and bundling. Prefer **`bun`** and **`bunx`** over `npm`, `npx`, or invoking Node directly for project commands and one-off CLI tools.

### Key commands

| Task             | Command                                               |
| ---------------- | ----------------------------------------------------- |
| Install deps     | `bun install`                                         |
| Lint markdown    | `bun run lint:md`                                     |
| Format markdown  | `bun run format:md`                                   |
| Run a `.ts` file | `bun run <file>.ts`                                   |
| Type-check       | `bunx tsc --noEmit` (no `.ts` source files exist yet) |

### Notes

* There is no application server, database, or frontend — the project is in bootstrap stage.
* The sole runtime dependency is `csv-simple-parser` for CSV parsing.
* Bun must be on `$PATH`; it is installed to `~/.bun/bin`. If `bun` is not found, run `curl -fsSL https://bun.sh/install | bash`.
* Markdown lint/format uses `remark-cli` with GFM and preset lint rules configured in `package.json` under `remarkConfig`.
