# What is this?

This is my personal Neovim config. Feel free to take bits of it to build your own or run it yourself.

As this is my personal config I am bound to change it a lot, so I recommend forking rather than pointing to this config.

## Stack

- **nixpkgs**: `nixpkgs-unstable`
- **Neovim**: nightly build from [nix-community/neovim-nightly-overlay](https://github.com/nix-community/neovim-nightly-overlay), using the flake’s **package output** (not the full overlay) so tree-sitter vendor hashes stay aligned with that build.
- **Nix LSP**: [nixd](https://github.com/nix-community/nixd) via `nvim-lspconfig` (not the archived `rnix-lsp`).

## How to use

From a clone of this repository:

```bash
nix run
```

or explicitly:

```bash
nix run .#default
# same binary:
nix run .#nvim
```

Without cloning (uses this repo’s default app; substitute your fork if needed):

```bash
nix run github:bastiion/neovim-flake
```

## How to update

Refresh inputs (Neovim nightly, nixpkgs, plugin flakes, etc.):

```bash
nix flake update
```

Run that regularly if you want the latest nightly from `neovim-nightly-overlay`. You can add [nix-community’s Cachix](https://app.cachix.org/cache/nix-community) to avoid building Neovim from source when possible.

## Folder structure

```
|- lib/        -- utility functions (e.g. neovimBuilder)
|- modules/    -- NixOS-style modules that generate init / Lua config
|- flake.nix   -- flake inputs and package/app outputs
|- README.md   -- this file
```

## License

The files and scripts in this repository are licensed under the MIT License, which is a very permissive license allowing you to use, modify, copy, distribute, sell, give away, etc. the software. In other words, do what you want with it. The only requirement with the MIT License is that the license and copyright notice must be provided with the software.
