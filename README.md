# `pdfify`

Generates Octocat-friendly PDFs from Markdown.

## Installation

```bash
brew cask install wkhtmltopdf  # see note below
brew tap swinton/brews
brew install pdfify
```

:warning: Due to [an existing `wkhtmltopdf` bug](https://github.com/wkhtmltopdf/wkhtmltopdf/issues/3241), until this gets fixed, you may want to manually install [an earlier version of `wkhtmltopdf`](http://download.gna.org/wkhtmltopdf/0.12/0.12.3/).

## Usage

```bash
pdfify /path/to/some/markdown/file.md
```

This will generate a PDF, `/path/to/some/markdown/file.pdf`.

## Advanced usage

### Page breaks

To insert a page break, include a `{.page-break}` header attribute.

For example, the following will cause a page break to be inserted _before_ the Lorem ipsum header:

```markdown
# Lorem ipsum {.page-break}

Lorem ipsum dolor sit amet...
```

### Customized styles

To customize the default stylesheet, create a `~/.pdfify/style.css` based off [the included `lib/style.css`](https://github.com/swinton/pdfify/blob/master/lib/style.css).

### Customized header / footer

To customize the default header or footer, create a `~/.pdfify/header.html` / `~/.pdfify/footer.html` based off [the included equivalents](https://github.com/swinton/pdfify/blob/master/lib/).
