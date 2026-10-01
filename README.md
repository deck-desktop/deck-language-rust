# Rust for Deck

rust-analyzer, for `.rs`. A project is anything with a `Cargo.toml`.

```sh
rustup component add rust-analyzer
```

## Colours

Fifty-one token rules, which is not excess: rust-analyzer has one of the richest semantic token
legends of any server, and every type it emits needs a rule or it renders unstyled — a semantic
token with no colour overrides the grammar with nothing. Lifetimes, macros, unsafe functions and
mutable bindings are each distinguished here.

## Status

`experimental/serverStatus` drives the readout, so the status dot says "indexing" while
rust-analyzer is still working through a workspace rather than appearing idle.

`checkOnSave` runs `cargo check` on save, which is where the diagnostics come from.

## Installing it

From inside Deck: **Settings -> Plugins -> Browse**, pick it, and it loads straight away.

By hand: copy this folder into `%APPDATA%\Deck\languages\` (`Deck-Dev` for a debug build).
`docs/languages.md` in the Deck repository documents the format.

## What a definition can and cannot do

It is **data**, not code. `language.json` is parsed field by field and never executed, which is
why a language is a different kind of thing from a plugin even though both are folders Deck
reads at startup. The worst a malformed one can do is skip itself.
