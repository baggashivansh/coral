# Hashnode Community Source

**Version:** 0.1.0  
**Backend:** HTTP  
**Tables:** 1  
**Base URL:** `https://gql.hashnode.com`

Query and discover Hashnode developer blogs, articles, and publication metadata.

```bash
coral source add --file sources/community/hashnode/manifest.yaml
```

## Tables

| Table | Description |
|---|---|
| `posts` | Fetch Hashnode article and publication metadata |

---

## `posts`

Fetch developer blog post metadata from Hashnode.

### Columns

| Column | Type | Description |
|---|---|---|
| `title` | Utf8 | Article title |
| `slug` | Utf8 | Post slug |
| `brief` | Utf8 | Short article summary |
| `author` | Utf8 | Article author |
| `publication` | Utf8 | Publication or blog name |

---

## Quick start

```bash
coral sql "
  SELECT title, author, publication
  FROM hashnode.posts
  LIMIT 10
"
```

## Notes

- Hashnode is widely used for engineering blogs and developer focused publishing.
- Useful for developer content discovery and indexing workflows.
- Uses the public Hashnode GraphQL API.