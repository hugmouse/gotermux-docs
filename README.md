# GoTermux documentation

> [!WARNING]
> This documentation will no longer receive any updates.

This repo contains documentation for [GoTermux](https://github.com/hugmouse/gotermux).

Build on [Hugo](https://gohugo.io), uses [HuDocs](https://github.com/zkreations/docs) theme.

## Build process

Latest tested version of Hugo is `v0.147.0+extended`.

To build, use `hugo build`. To have a live preview, use `hugo serve --disableFastRender`.

## Contributing

For more information about Termux and its capabilities, you might find these links helpful:

- [Termux Wiki](https://wiki.termux.com/wiki/Main_Page): Contains documentation for all things Termux.
- [Termux:API](https://wiki.termux.com/wiki/Termux:API): Documentation for the Termux API.
- [Termux on GitHub](https://github.com/termux/termux-app): The official GitHub repository for the Termux application.

Output of Termux API command vary from device to device and versions of Termux itself.

----

Since the documentation uses the HuDocs theme, you may want to use some of its additional features — such as advanced code blocks.

- [HuDocs - Overview](https://hudocs.com/en/1.0/starting/): The official HuDocs documentation.

## Recommendations

When using `hugo serve` also use `--disableFastRender` otherwise you might be served cached content even when you
changed a thing or two. Also, sometimes it helps to completely obliterate `public` and `resources` folders that 
are created by `hugo serve`.
