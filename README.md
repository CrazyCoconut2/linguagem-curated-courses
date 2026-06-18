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
  en-es/                       # user_lang-target_lang
    spain-regional-expressions.linguagem
    beginner-spanish/          # optional cursus subfolder
      lesson-1.linguagem
  fr-es/
    ...
catalog.json                   # index of available databases
```

Paths follow `databases/{user_lang}-{target_lang}/[{cursus}/]{name}.linguagem`:

- **user_lang** — language the learner already speaks (matches app UI language)
- **target_lang** — language being studied
- **cursus** — optional subfolder for a course track or series

Use kebab-case filenames that describe the collection.

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md) for how to add or update a database.

## License

Individual databases may specify their own license in `catalog.json`. Unless stated otherwise, contributions are shared under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
