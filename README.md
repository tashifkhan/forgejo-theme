# Forgejo Theme

Color themes for Zed and VS Code ported from Forgejo's official
`forgejo-dark` / `forgejo-light` web themes, i.e. the same design tokens
that power [git.taf.sh](https://git.taf.sh).

Two variants in one family:

| Theme          | Appearance | Source                                            |
| -------------- | ---------- | ------------------------------------------------- |
| **Forgejo Dark**  | dark       | `web_src/css/themes/theme-forgejo-dark.css` + `chroma/dark.css` |
| **Forgejo Light** | light      | `web_src/css/themes/theme-forgejo-light.css` + `chroma/light.css` |

Surfaces use Forgejo's steel scale (`#10161d` navbar → `#171e26` body →
`#1d262f` code), the primary is Forgejo orange (`#fb923c` dark / `#c2410c`
light), and syntax colors come 1:1 from the Chroma highlighting palette your
instance renders code blocks with. The integrated terminal keeps Forgejo's
Actions-console look (`#1f212b` + its `--color-ansi-*` palette).

## Layout

```
zed/       Zed extension (extension.toml + themes/forgejo.json)
vscode/    VS Code extension (package.json + themes/*.json + icon)
```

## Install locally

### Zed

```bash
mkdir -p ~/.config/zed/themes
cp zed/themes/forgejo.json ~/.config/zed/themes/
```

Restart Zed, then `theme selector: toggle` (cmd-k cmd-t) → **Forgejo Dark**
or **Forgejo Light**.

### VS Code

```bash
cd vscode
npx @vscode/vsce package
code --install-extension forgejo-theme-0.1.0.vsix
```

Then `Preferences: Color Theme` → **Forgejo Dark** / **Forgejo Light**.

## Publishing

- Zed: fork `zed-industries/extensions`, add the extension as a git submodule
  + an entry in `extensions.toml`, open a PR.
- VS Code: create a publisher on the Marketplace, `vsce publish` with an
  Azure DevOps PAT; mirror to Open VSX with `ovsx publish`.

Full write-up: <https://dump.taf.sh>

## License

MIT. Forgejo's color values come from the Forgejo project (MIT).
