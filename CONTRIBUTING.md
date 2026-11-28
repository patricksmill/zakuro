# Contributing

Thanks for helping with the Kid Icarus: Uprising PC port.

## Reporting

[Open an issue](https://github.com/patricksmill/UprisingHack/issues/new/choose) and pick a form:

- **Bug report**: a crash, wrong behaviour or a regression. Try the latest [nightly](https://github.com/patricksmill/UprisingHack/releases/tag/nightly) first, and say which build you used.
- **Screen change**: how one Screen looks or responds.
- **Feature request**: something new.

Never attach game data: no dumps, `code.bin`, save states or extracted assets.

## Building

See [docs/BUILDING.md](docs/BUILDING.md). You need your own decrypted dump of the game. Before opening a pull request, run:

```sh
cargo test --release --workspace
```

## Pull requests

Pick the template that fits, by adding `?template=<name>.md` to the compare URL or passing `--template <name>.md` to `gh pr create`:

| Template | For |
| --- | --- |
| `screen.md` | One Screen's look or input |
| `feature.md` | Something new |
| `bugfix.md` | A fix |
| `chore.md` | Build, CI, docs, refactors, upstream merges |

Keep each pull request to one change, and open it against `patricksmill/UprisingHack`, not upstream Zakuro.

## Conventions

- Use the terms in [GLOSSARY.md](GLOSSARY.md).
- Write Screen changes as in [docs/agents/change-requests.md](docs/agents/change-requests.md): Operation, Target, Screen, before → after, Acceptance.
- Screens follow [docs/agents/screen-transform.md](docs/agents/screen-transform.md): draw and hit-test share one Placement list.
- Menu input calls the game's own functions; it doesn't fake button presses.
- Port-only files go in `kiu/` where possible, so upstream merges stay clean.
- Game addresses go in [kiu/analysis/FINDINGS.md](kiu/analysis/FINDINGS.md), not in code comments or docs.
- Record larger decisions as an ADR in [docs/adr/](docs/adr/).

## License

Contributions are licensed under the [MIT license](LICENSE), like the rest of the port.
