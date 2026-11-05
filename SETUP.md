# Setup: code and a YouTube API key

## 1. Open the code

Type **github.com/manueltonneau/hpi-api** on your laptop. Click **Open in Colab** in the README. Sign in with a Google account if needed, then use **File → Save a copy in Drive**. You can work in pairs.

The notebook is self-contained. It does not need a GPU, YouTube downloads, Whisper or a separate data upload. Pandas and requests are the core packages; install them in a notebook cell with `%pip install pandas requests` if needed.

## 2. Create a standard API key

You need a Google account and permission to create a Google Cloud project. An institution-managed account may restrict project or key creation; if blocked, use the offline exercise or pair with someone who has working access.

1. Open the [Google Cloud console](https://console.cloud.google.com/) and sign in.
2. Use the project selector near the top: **New project → name the project → Create**. Select that project.
3. Go to **APIs & Services → Library**. Search for **YouTube Data API v3**, open it, and click **Enable**.
4. Go to **APIs & Services → Credentials → Create credentials → API key**. Name the key. Under **API restrictions**, choose **Restrict key → YouTube Data API v3**. Leave **Authenticate API calls through a service account** unchecked, then click **Create**. We need a standard API key, not OAuth or a service-account key.
5. If your console creates the key immediately, open its details to apply that API restriction and save. Application restrictions must match where your code runs; a browser-referrer restriction can block Python/Colab requests. Follow the official guidance rather than applying a mismatched restriction.
6. Keep the key private. You can return to the Credentials page to manage or delete it after use.

Official instructions: [YouTube getting started](https://developers.google.com/youtube/data/getting-started), [public-data API-key authentication](https://developers.google.com/youtube/data/guides/authentication), and [managing API keys](https://docs.cloud.google.com/docs/authentication/api-keys).

## 3. Use the key in the notebook

In the first configuration cell:

```python
OFFLINE = False
```

Run the cell. A hidden input prompt appears if `YOUTUBE_API_KEY` is not already set. Paste your key there. Do not replace the environment-variable code with a literal key, print the key, or print a complete credential-bearing request URL.

Run the setup and guided example in order. A successful first search and metadata request confirm that the key can call the API. If you switch modes, restart the runtime/kernel and rerun from the top.

## 4. Choose your project

Use [PROJECTS.md](PROJECTS.md) and notebook section 4. Pick `PROJECT_KIND`, edit its request dictionary, then run the collector and descriptive summary. IDs are not whole URLs: a video ID is the value after `v=` in a watch URL; a channel ID can be obtained with the optional finder in the notebook.

## If something blocks you

- **No key yet:** leave `OFFLINE=True`. The guided exercise and local exploration work with the embedded saved videos. New sources, channel statistics and comments are live-only.
- **HTTP 403:** read the reason. Check that the right project has YouTube Data API v3 enabled, that the key restrictions permit the call, and that quota remains. An error response is not an empty dataset.
- **Comments disabled:** choose another video or a different project; some videos expose no public comment threads.
- **No/fewer records:** inspect filters, dates and returned IDs. A requested page size is a maximum.
- **Saving in Colab:** download `project_records.csv` and `manifest.json` from the file browser under `workshop_outputs/<run_id>` before ending the runtime.

Do not let account setup consume the whole practical. Start with the offline example and return to live setup when you can.
