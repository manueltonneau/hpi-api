# Choose a project

Pick a question, set `PROJECT_KIND`, then edit the matching request dictionary.

| Template | Edit | Example summary |
| --- | --- | --- |
| `channel_videos` | `channelId`, dates, order, size | Mean/median views |
| `topic_videos` | `q`, dates, order, size | Returned videos per channel |
| `channel_statistics` | One or more channel `id` values | Reported public videos/subscribers |
| `video_comments` | `videoId`, order, size | Text length, likes, reply counts |

## Find a channel ID

1. Open any YouTube channel; copy its **@handle**.
2. In the notebook’s channel finder, set `RUN_CHANNEL_DISCOVERY=True` and enter the handle in `CHANNEL_LOOKUP`.
3. Run the cell. Check the returned title, then copy the ID into your request (`channelId` for video search, `id` for channel statistics).

You can also search a channel name. Topic searches need no channel ID. AfD is only the supplied example.

[Parameters and official documentation](PARAMETERS.md)

Keep **20 results per page, at most two pages**. Describe the returned records, not the whole platform. Comments are top-level only; share aggregate summaries rather than identifying quotes.
