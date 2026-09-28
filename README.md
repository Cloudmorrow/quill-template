# Quill template

The starting point for a [Quill](https://github.com/Cloudmorrow/cloudmorrow/blob/main/docs/QUILLS.md):
a package that adds data, screens and what can be done with them to a
Cloudmorrow — on the phone, in the browser, in the terminal, on the command
line and to an assistant. It is TOML and Python and nothing else: no UI code,
ever. [QUILLCODE.md](https://github.com/Cloudmorrow/cloudmorrow/blob/main/docs/QUILLCODE.md)
is the contract for the Python.

## Start

Either press **Use this template** above (not *Fork*: a fork stays tied to
this repository), or let the command line make one with your names filled in:

```sh
pip install "cloudmorrow[tui] @ git+https://github.com/Cloudmorrow/cloudmorrow"
cm quill new plants --name Plants --summary "Your plants, and when you last watered each."
```

If you used the template button, replace `example` with your Quill's id in
`quill.toml`, `quill.py`, `tests/test_quill.py`, `pyproject.toml` and
`datamodels/item.toml`.

## What is in it

| | |
| --- | --- |
| `quill.toml` | everything the Quill is and does: a datamodel, an overview drawn by code, a list, and two actions |
| `quill.py` | the code behind the overview and the actions, run in a sandbox as whoever uses them |
| `datamodels/` | the one datamodel it introduces, `example.item` |
| `tests/` | tests against the real record store and gate, with `cloudmorrow.quill.testing` |
| `CLAUDE.md`, `.claude/skills/` | how an assistant works on it: screens, actions, data, automation, machines, testing, publishing |
| `.github/workflows/` | check and test on every push, in plain Python and in the sandbox; a release on a `v*` tag |
| `pyproject.toml` | for working on it: `uv sync` gets Cloudmorrow and pytest |

## The loop

```sh
uv sync                  # .venv with Cloudmorrow and pytest
cm quill check           # the manifest against the foundational datamodels, and a preview of every screen
cm quill test            # tests/, against the real record store and gate
cm quill test --sandbox  # the same, with quill.py in the sandbox, as a server runs it
cm quill preview         # the overview, drawn as text
cm quill dev --local     # a throwaway server on this machine, reinstalled as you save
cm quill dev             # install it on your own server, on every device, now
```

Or open the folder with an assistant: [CLAUDE.md](CLAUDE.md) and the skills
teach it the format and the loop, and it can drive every command itself.

## Publishing

Tag a release (`v0.1.0`, the same as `version` in `quill.toml`) and open a
pull request on [Cloudmorrow/quill-catalog](https://github.com/Cloudmorrow/quill-catalog)
adding it to `catalog.toml`.
