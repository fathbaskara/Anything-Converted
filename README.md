# csv2md

CSV to Markdown table. Python 3 stdlib only — no dependencies.

Linux for now; macOS and Windows later.

## Install

```bash
install -m 755 csv2md ~/.local/bin/csv2md
```

Needs `~/.local/bin` on `PATH`.

## Usage

```bash
csv2md data.csv                 # table to stdout
csv2md data.csv -o table.md     # table to file
cat data.csv | csv2md           # read stdin
csv2md data.csv -d ';'          # force delimiter
```

The delimiter is auto-detected from `,`, `;`, tab and `|`, falling back to `,`.
A UTF-8 BOM is stripped, and ragged rows are padded to the widest row.

## Example

```
$ printf 'service,price\nDeep clean,Rp 150.000\n' | csv2md
| service    | price      |
| ---------- | ---------- |
| Deep clean | Rp 150.000 |
```

## License

MIT
