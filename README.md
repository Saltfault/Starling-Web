# Starling Web

Browser client for **[Starling](https://forgejo.hearthhome.lol/Saltfault/Starling)** — a federated, peer-to-peer communications platform with no company in the middle.

> **Status: 📋 Planned — not yet started.**
> The terminal client, **[Starling-TUI](https://forgejo.hearthhome.lol/Saltfault/Starling-TUI)**, is the working client today. This repo is a placeholder for the WebAssembly build.
> The web client needs no install — it'll just be a hosted page you open in a browser.

---

## What this will be

Starling with nothing to install: open a page, paste an invite code, and you're in the flock. The web client is how someone tries Starling for the first time without a terminal or a download — text, voice, and video in the browser, still peer-to-peer and end-to-end encrypted.

## How it's built (planned)

The **same Solid.JS frontend** as the desktop and Android clients, delivered in the browser instead of a Tauri shell — so the UI is shared across all three. The [`starling-server`](https://forgejo.hearthhome.lol/Saltfault/Starling-Server) core is compiled to **WebAssembly** to run in-page. The interesting engineering is in the browser's constraints, not the protocol.

| Piece | Stack |
|-------|-------|
| Frontend | Solid.JS (shared with Desktop + Android) |
| Protocol / networking | [`starling-server`](https://forgejo.hearthhome.lol/Saltfault/Starling-Server) core, compiled to `wasm32` |
| Transport note | iroh over the browser uses WebTransport/relays; the datagram-vs-stream media paths may need browser-specific handling |
| Media | `getUserMedia` for mic/camera; WASM Opus for audio |

## Following along

- Design and roadmap live in the main **[Starling](https://forgejo.hearthhome.lol/Saltfault/Starling)** repo.
- The protocol this will implement is documented in **[Starling-Server](https://forgejo.hearthhome.lol/Saltfault/Starling-Server)**.

## License

Apache 2.0
