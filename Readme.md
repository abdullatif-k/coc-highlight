# coc-highlight

Provide default highlight for [coc.nvim](https://github.com/neoclide/coc.nvim),
including document highlight (highlight of current document symbol) and colors
highlight.

<img width="480" alt="Screen Shot 2019-07-01 at 9 11 33 AM" src="https://user-images.githubusercontent.com/251450/60405074-979ae080-9be0-11e9-8039-b9a48fd8b5ad.png">

## Install

In your vim/neovim, run command:

```
:CocInstall coc-highlight
```

## Features

- Highlight symbol of current position in all positions of current buffer (when no document
  highlight provider exists from language server).
- Highlight colors of current buffer (when no color provider exists from
  language server).

## Usage

To enable highlight current symbol on `CursorHold`, add:

```vim
autocmd CursorHold * silent call CocActionAsync('highlight')
```

to your `.vimrc`.

To disable coc provide color highlight, add:

```json
"coc.preferences.colorSupport": false,
```

to your `settings.json`.

To pick a different color, use command:

```
:call CocAction('pickColor')
```

**Note:** only works on Mac or have python gtk module installed.

To pick a different color presentation, use command:

```
:call CocAction('colorPresentation')
```

## Options

- `highlight.disableLanguages`, list of filetypes to ignore for this extension.
- `highlight.document.enable`, set to `false` to disable document symbol
  highlight.
- `highlight.colors,enable`, set to `false` to disable color highlight.

## F.A.Q

**Q:** Why color highlight is not shown on my vim?

**A:** First, make sure `"coc.preferences.colorSupport"` is not `false` in your
`coc-settings.json`, then make sure you have `set termguicolors` in your `.vimrc`,
and your terminal support true color.

**Q:** How to change highlight of the current symbol.

**A:** All you need is overwrite the highlight group, checkout `:h coc-highlights`

## License

MIT
