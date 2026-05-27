# Hashnode Coral Source

Query Hashnode publication posts using the official Hashnode GraphQL API through Coral.

This source provides access to publication posts, author metadata, publication details, and article information using Hashnode's supported GraphQL API surface.

---

## Requirements

Hashnode GraphQL API access is required.

As of May 2026, Hashnode no longer provides unrestricted public GraphQL API access. You must have valid API access and a personal access token configured before using this source.

References:
- https://hashnode.com/changelog/2026-05-13-graphql-api-paid-access
- https://apidocs.hashnode.com/

---

## Setup

Export your Hashnode API token:

```bash
export HASHNODE_API_TOKEN=your_token_here
```

Add the source:

```bash
coral source add hashnode
```

---

## Available Tables

### publication_posts

Fetch posts from a Hashnode publication using the official GraphQL API.

---

## Example Queries

Fetch recent publication posts:

```sql
SELECT title, author_name, published_at
FROM hashnode.publication_posts
LIMIT 5;
```

Fetch post URLs and summaries:

```sql
SELECT title, brief, url
FROM hashnode.publication_posts
LIMIT 10;
```

Fetch publication information:

```sql
SELECT title, publication_title
FROM hashnode.publication_posts
LIMIT 5;
```

---

## Example Output

| title | author_name | publication_title |
|------|------|------|
| Building Better APIs | John Doe | Engineering Blog |
| Scaling GraphQL Systems | Jane Smith | Backend Weekly |

---

## Supported Features

- Publication post retrieval
- Author metadata
- Publication metadata
- Cursor pagination
- GraphQL-based querying

---

## Limitations

- Requires Hashnode API access
- Requires authentication token
- Scoped to publication post queries
- Depends on Hashnode GraphQL API availability and limits

---

## Pagination

This source supports cursor pagination using Hashnode GraphQL `pageInfo.endCursor` and `hasNextPage`.

---

## Testing

Run source validation:

```bash
coral source lint
```

Run source tests:

```bash
coral source test
```

---

## References

- https://apidocs.hashnode.com/
- https://docs.hashnode.com/
- https://docs.hashnode.com/quickstart/hashnode-graphql-api-quickstart/how-to-fetch-posts-from-your-blog
