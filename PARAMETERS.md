# Request parameters

Start with the notebook templates. The official endpoint pages list all accepted parameters, values and response fields.

## Video search — [official documentation](https://developers.google.com/youtube/data/reference/rest/v3/search/list)

| Parameter | Meaning | Example |
| --- | --- | --- |
| `q` | Search phrase | `"climate policy"` |
| `channelId` | Restrict to one channel | ID from the channel finder |
| `order` | Result ordering | `"date"`, `"viewCount"`, `"relevance"` |
| `maxResults` | Maximum records on one page | `10` |
| `publishedAfter` / `publishedBefore` | Publication window (UTC) | `"2026-01-01T00:00:00Z"` |

Keep `part="snippet"` and `type="video"` in these search templates. Language relevance is not a strict language filter; region availability is not uploader nationality.

## Video details — [official documentation](https://developers.google.com/youtube/data/reference/rest/v3/videos/list)

- `id`: comma-separated video IDs returned by search.
- `part`: `snippet` (e.g. title), `statistics` (counts), `contentDetails` (e.g. duration).

## Channels — [official documentation](https://developers.google.com/youtube/data/reference/rest/v3/channels/list)

- `forHandle="@GoogleDevelopers"`: look up a channel’s ID by handle.
- `id`: one or more known channel IDs; use this for the statistics project.
- `part="snippet,statistics"`: name, subscribers, reported public-video count and total views.

Use `forHandle` **or** `id`, not both. The notebook finder handles the lookup for you.

## Comments — [official documentation](https://developers.google.com/youtube/data/reference/rest/v3/commentThreads/list)

- `videoId`: one video ID, not its full URL.
- `order`: `"time"` (recent) or `"relevance"`.
- `maxResults`: page size. The template uses `textFormat="plainText"` and collects top-level comments only.

The workshop caps search/comments at **20 per page and two pages**. `PROJECT_MAX_PAGES` is our collection setting, not a YouTube parameter; the collector sends each returned `nextPageToken` back as `pageToken`.
