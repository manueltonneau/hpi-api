# Choose a question and a request

Start small and describe the records you actually obtain. These are starting points, not mandatory research questions.

## Videos from a channel

Possible question: *How do views vary among a small set of videos returned for this channel?*

Choose `PROJECT_KIND = "channel_videos"`. Edit `channel_video_request`: channel ID, `order`, `maxResults`, optional `q`, `publishedAfter` and `publishedBefore`. Compare the median and mean views or the distribution of likes/comments. Search does not guarantee a complete channel upload history.

## Videos about a topic

Possible question: *Which channels account for the returned videos about this search phrase?*

Choose `PROJECT_KIND = "topic_videos"`. Edit `topic_video_request`. Summarise the number of returned videos per channel, their publication dates or their view counts. Relevance ranking and keywords select a particular set; do not treat it as all discussion of the topic.

## Channel-level statistics

Possible question: *How do a few deliberately chosen channels compare in reported public video counts or subscribers?*

Choose `PROJECT_KIND = "channel_statistics"`. Use the optional channel finder, verify identities, and put one or more comma-separated IDs into `channel_statistics_request["id"]`. The `channels` endpoint can return the reported number of **public** videos without downloading all their metadata. Subscriber counts may be hidden or rounded. These are selected channels, not a random sample of creators.

## Comments on a video

Possible question: *What are the text lengths, likes and reply counts of the returned top-level comments?*

Choose `PROJECT_KIND = "video_comments"`. Edit `comment_request`: `videoId`, `order="time"` or `"relevance"`, and `maxResults`. We request plain text and a limited set of fields, omitting author identifiers from the default response. We collect top-level comments only; reply text is not collected. A reply count does not mean you have the replies themselves.

Some videos disable comments. A recent/relevance selection is not representative of all comments or viewers. Text can contain personal information even without author fields; share aggregate summaries rather than identifying quotes.

## Small collection, clear summary

The collector limits video/comment requests to at most two pages of 20 records each. It stops at the budget even if another page exists. Keep request settings comparable when comparing groups.

Prepare: **question → request → one result → one limitation**. A table or simple chart is enough; presenting to the class is optional.
