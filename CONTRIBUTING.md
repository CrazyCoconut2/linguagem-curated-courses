# Contributing

Thank you for helping build curated databases for Linguagem learners.

## Adding a database

1. **Create or export** a database in the Linguagem app (or author the JSON by hand).
2. **Save** it under `databases/{user-lang}-{target-lang}/[{cursus}/]your-database-name.linguagem`.
   - `{user-lang}` is the learner's language (`en`, `fr`, `pt`, …).
   - `{target-lang}` is the language being studied (`es`, `pt`, `fr`, …).
   - `{cursus}` is an optional subfolder for a course track or series.
   - Use a descriptive kebab-case filename.
3. **Add an entry** to [catalog.json](./catalog.json).
4. **Open a pull request** with a short description of what the database covers.

## Updating a database

- Bump the `version` field in `catalog.json` when you make meaningful changes.
- Prefer adding capturables over rewriting existing ones, so learners who already imported the database are not surprised.

## Database format

A valid `.linguagem` file is JSON with at least:

```json
{
  "Configuration": [
    {
      "class": "Configuration",
      "databaseName": "My Collection",
      "targetLanguage": "es",
      "createdAt": 1710000000000,
      "description": "Optional description shown in the app."
    }
  ],
  "Capturables": [
    {
      "id": 1,
      "class": "Capturable",
      "content": "vale",
      "lastSeen": 0,
      "captureConfiguration": { "pattern": ["vale"] },
      "definitions": [
        {
          "content": "OK, sure (Spain, informal)",
          "examples": [
            {
              "content": "Vale, nos vemos mañana.",
              "translations": { "en": "OK, see you tomorrow." },
              "metadata": { "source": "user-added" }
            }
          ]
        }
      ],
      "metadata": { "tags": ["spain", "informal"] }
    }
  ]
}
```

### Capturable guidelines

- **content** — lowercase, trimmed; this is the headword or phrase learners capture.
- **captureConfiguration.pattern** — usually matches `content`; can include regex patterns for advanced cases.
- **definitions** — optional but encouraged; include at least one example when possible.
- **metadata.tags** — use consistent tags (`regional`, `informal`, `course`, `a1`, …) to help learners filter.
- **lastSeen** — use `0` for curated entries that have not been studied yet.

### What belongs here

- Course-style vocabulary lists
- Regional or dialectal expressions
- Themed collections (slang, food, travel, …)
- Anything expressible as Linguagem capturables

### What to avoid

- Copyrighted material you do not have rights to share
- Duplicate databases that overlap heavily with an existing entry
- Empty or placeholder databases

## catalog.json fields

| Field | Description |
|-------|-------------|
| `id` | Stable slug, matches the filename without extension |
| `name` | Display name |
| `description` | One or two sentences |
| `userLanguage` | Learner's language (first part of `databases/{user-lang}-{target-lang}/…`) |
| `targetLanguage` | Language being studied (second part of `databases/{user-lang}-{target-lang}/…`) |
| `cursus` | Optional slug when the file lives in a cursus subfolder |
| `tags` | Optional labels for browsing |
| `authors` | GitHub username or name |
| `version` | Semver (`1.0.0`) |
| `file` | Path to the `.linguagem` file from repo root |

## Questions

Open an issue if you are unsure whether a database fits, or if you need help with the file format.
