# vscode-lbnf

[![Version](https://vsmarketplacebadge.apphb.com/version/agurodriguez.vscode-lbnf.svg)](https://marketplace.visualstudio.com/items?itemName=agurodriguez.vscode-lbnf) [![Installs](https://vsmarketplacebadge.apphb.com/installs-short/agurodriguez.vscode-lbnf.svg)](https://marketplace.visualstudio.com/items?itemName=agurodriguez.vscode-lbnf) 

An extension for VS Code which provides support for the [LBNF language](https://github.com/BNFC/bnfc/blob/master/docs/lbnf.rst#appendix-lbnf-specification).

LBNF is acronym for *Labelled BNF*, which is the language used in the compiler construction tool [BNF Converter](https://github.com/BNFC/bnfc).

![](docs/screenshot.png)

## Features

* Syntax highlighting

## Development

1. Install dependencies:

```bash
npm install
```

2. Open this folder in VS Code and press F5 to launch an Extension Development Host.

## Packaging

Build a `.vsix` package locally:

```bash
npx @vscode/vsce package
```

This produces a file like `vscode-lbnf-1.0.5.vsix` in the repository root.

## Publishing

There are two stores you can publish to.

### Visual Studio Marketplace (VS Code)

1. Install the CLI:

```bash
npm i -g @vscode/vsce
```

2. Create a Personal Access Token (PAT) on Azure DevOps with scope "Marketplace (publish)".
3. Sign in once (stores token locally):

```bash
vsce login agurodriguez
```

4. Publish a new version (ensure `version` in `package.json` is bumped):

```bash
vsce publish
```

### Open VSX Registry (for VSCodium, etc.)

1. Install the CLI:

```bash
npm i -g ovsx
```

2. Create an Open VSX token at `https://open-vsx.org` and set it as env var:

```bash
export OVSX_TOKEN=your-token-here
```

3. Publish:

```bash
ovsx publish
```

Alternatively, use the npm scripts:

```bash
npm run package
npm run publish:vsce
npm run publish:ovsx
```

## Release Notes

### 1.0.5

- Fix issue with strings containing a semicolon in rules starting with a keyword

### 1.0.4

- Fix issue with word `nonempty` not being detected when placed next to another keyword

### 1.0.3

- Fix issue detecting single line comments after rules starting with a keyword

### 1.0.2

- Fixed issues detecting categories inside squared brackets
- Fixed issues parsing multiline rules

### 1.0.1

Added keywords for vscode marketplace

### 1.0.0

Initial release
