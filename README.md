# Linguagem Curated Courses

Community-curated databases for the [Linguagem](https://github.com/linguagem) app. Each database is a `.linguagem` file you can import to study vocabulary, regional expressions, or full course-style word lists.

## How to use a database

1. Browse [catalog.json](./catalog.json) or the `databases/` folder.
2. Download a `.linguagem` file.
3. In the Linguagem app, go to **Databases** and import the file.

The app accepts the standard Linguagem export format: a JSON file with `Configuration` and `Capturables` stores.

## Repository layout

```
databases/
  es/                          # target language code
    spain-regional-expressions.linguagem
  pt/
    ...
catalog.json                   # index of available databases
```

Files are grouped by **target language** (`en`, `es`, `fr`, `pt`, …). Use kebab-case filenames that describe the collection.

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md) for how to add or update a database.

## License

Individual databases may specify their own license in `catalog.json`. Unless stated otherwise, contributions are shared under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
