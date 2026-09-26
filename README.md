# Quill template

The starting point for a [Quill](https://github.com/Cloudmorrow/cloudmorrow/blob/main/docs/QUILLS.md):
a package that adds data and screens to a Cloudmorrow — on the phone, in the
browser, in the terminal, on the command line and to an assistant — with no UI
code at all.

## Start

Either press **Use this template** above, or let the command line make one
with your names filled in:

```sh
pip install "cloudmorrow[tui] @ git+https://github.com/Cloudmorrow/cloudmorrow"
cm quill new plants --name Plants --summary "Your plants, and when you last watered each."
```

If you used the template button, replace `example` with your Quill's id in
`quill.toml` and `datamodels/item.toml`.

## The loop

```sh
cm quill check     # the manifest against the foundational datamodels, and a preview of every screen
cm quill dev       # install it on your own server, on every device, now
```

Or open the folder with an assistant: [CLAUDE.md](CLAUDE.md) teaches it the
format and the loop, and it can drive both commands itself.

## Publish

Tag a release (`v1.0.0`) and open a pull request on
[the Quill Catalog](https://github.com/Cloudmorrow/quill-catalog) adding it.

## What it adds to your Cloudmorrow

Keep this table true; the catalog page shows it.

| | |
| --- | --- |
| Datamodels | introduces `example.item` |
| Screens | one list, on the phone, the web app, the terminal, `cm example`, and to your assistant |
| Jobs, datasets, services | none |

The template is MIT-licensed, so a Quill made from it may use any licence.
