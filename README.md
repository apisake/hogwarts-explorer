# The Marauder's Index

A one-page explorer for the wizarding world, built on the [Hogwarts API](https://hogwarts-api.com/), with Harry Potter at the centre.

- **Harry's page** (the home page): portrait, rotating nicknames, house, wand, patronus and boggart, plus his friends, foes, family, loves, seven years at Hogwarts (books and films) and signature spells
- **Explore** all six collections: characters, books, movies, spells, potions and creatures, with search and paging
- **Detail pages** with every field, book chapter summaries, movie trailers, clickable family members and the raw JSON

## Run it

Serve the folder (the saved data in `data/` can't be loaded from a `file://` page):

```bash
python3 -m http.server 8765
```

then visit http://localhost:8765.

## Where the data comes from

The app first tries the live API at `https://hogwarts-api.com/api`. At the moment the API doesn't send the CORS header browsers need, so web pages on other sites can't read it. When that happens, the app reads `data/*.json`, a copy of all 6,084 records saved on 2 November 2026, and uses the same paging and search rules as the API. The footer says which source is in use.

Data is compiled by the Hogwarts API from Potter DB and the [Harry Potter Wiki](https://harrypotter.fandom.com), licensed CC-BY-SA. This is an unofficial fan project with no affiliation to Warner Bros. or J.K. Rowling.
