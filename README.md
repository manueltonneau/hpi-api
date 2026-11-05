# Collecting data with APIs — HPI

**Start here:** [Open the notebook in Colab](https://colab.research.google.com/github/manueltonneau/hpi-api/blob/main/api_workshop.ipynb)

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/manueltonneau/hpi-api/blob/main/api_workshop.ipynb)

Short address to type on your laptop: **github.com/manueltonneau/hpi-api**

A 90-minute Python workshop: understand APIs, make a small collection, describe it, and explain its limits. No local Jupyter installation is needed when using Colab. You can also download `api_workshop.ipynb` and run it locally with Python 3.10+.

## Get ready

1. Open the notebook using the link above. In Colab, choose **File → Save a copy in Drive** to keep your work.
2. For live collection, follow [SETUP.md](SETUP.md) to create a **YouTube Data API v3 key**. Do this before class if possible.
3. In the notebook, set `OFFLINE=False` and enter the key in the hidden prompt, or use the `YOUTUBE_API_KEY` environment variable. Do not put a key in a shared code cell.
4. Run the guided example, then choose your question and request template.

If account setup or a connection blocks you, leave `OFFLINE=True` and start with the ten embedded saved video records. No separate data-file upload is needed. Offline filtering is a local exercise, not a replay of live YouTube searches.

For local Jupyter, install the packages with `python -m pip install -r requirements.txt`. In a notebook, use `%pip install pandas requests` if an import fails. Plotting optionally requires matplotlib.

## Choose a collection

| Template | What you choose | What you can describe |
| --- | --- | --- |
| `channel_videos` | Channel ID, optional keywords/dates, ordering, page size | Views, likes, comments and publication dates among selected videos |
| `topic_videos` | Search phrase, date window, ordering, optional channel | Returned videos and their distribution across channels |
| `channel_statistics` | One or more verified channel IDs | Reported public video count, subscribers and total views |
| `video_comments` | A video ID, recent/relevance ordering, page size | A small set of top-level comments: text length, likes and reply counts |

Only video records from the supplied example are cached. New sources, channel-level statistics and comments require live access. The notebook includes an optional channel-ID finder and editable request dictionaries. Search and comments are limited to **20 results per page and two pages**; channel statistics to **20 selected channels**.

Choose the question first. Then identify your unit (video, channel or top-level comment), the fields you need, the request settings and a small collection budget. [Project ideas and examples](PROJECTS.md)

## Finish with a small result

Use counts, missingness, medians, means, ranges or a simple plot. Save the CSV and collection manifest. A search result is not automatically a representative sample; reported counts have definitions and observation times.

Prepare four lines: **question, request, one result, one limitation**. Sharing in class is voluntary, alone or in pairs, for about two minutes. No presentation slides are required.

## Attribution and data provenance

The guided search → video IDs → metadata → pandas workflow is adapted from the supplied teaching notebook attributed to Juan S. Gómez-Cruces. Audio download and transcription are outside this workshop. The ten offline records were reconstructed from displayed saved outputs; they are not original raw API responses, and their exact original observation time is unknown. A copy of their provenance is in `saved_video_records.json` and embedded in the notebook.

Teaching structure also draws on [Berkeley D-Lab](https://github.com/dlab-berkeley/Python-Web-APIs), [Katherine Walden](https://github.com/kwaldenphd/apis-python), and [Karsten T. Hansen / UCSD](https://bar.rady.ucsd.edu/CollectingDatawithAPI.html). Current endpoint behaviour is linked to official documentation within the notebook.
