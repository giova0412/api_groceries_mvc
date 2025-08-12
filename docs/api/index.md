# API Reference

No public symbols were detected because no source files were found in the repository yet.

Once code exists, generate API docs using one of the options below and commit the output under `docs/api/`:

## TypeScript / JavaScript
- Add JSDoc/TSDoc comments to your exports.
- Generate with TypeDoc:

```bash
npm i -D typedoc typedoc-plugin-markdown
npx typedoc --out docs/api --plugin typedoc-plugin-markdown src/index.ts
```

## Python
- Add docstrings to functions/classes.
- Generate with `pdoc`:

```bash
pip install pdoc
pdoc -o docs/api path/to/your_package
```

Or with Sphinx:

```bash
pip install sphinx sphinx-autodoc-typehints
sphinx-quickstart  # choose docs directory
sphinx-apidoc -o docs/source your_package
make -C docs html
```

## Java
- Use Javadoc comments and run:

```bash
javadoc -d docs/api -sourcepath src -subpackages com.yourorg
```

## Go

```bash
go doc -all ./... > docs/api/GO_DOCS.md
```

## Rust

```bash
cargo doc --no-deps
# Copy or link target/doc into docs/api as needed
```