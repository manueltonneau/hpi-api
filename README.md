# YouTube API practical — HPI

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/manueltonneau/hpi-api/blob/main/api_workshop.ipynb)

1. Open Colab → **File → Save a copy in Drive**.
2. [Create a YouTube API key](SETUP.md). Set `OFFLINE=False`; enter the key in the hidden prompt.
3. Run the guided example, then choose your question and request.
4. Summarise the results and save your CSV.

**No Python confidence?** Use the [fully worked example](https://colab.research.google.com/github/manueltonneau/hpi-api/blob/main/worked_example.ipynb): run the cells or read the saved output. No code writing needed.

**Choose freely:** videos from a channel, topic searches, channel statistics or video comments. AfD is only the guided example. [Project choices](PROJECTS.md) · [Parameters and official docs](PARAMETERS.md)

**No key?** Keep `OFFLINE=True` for ten saved videos. New sources, channel statistics and comments need live access.

Prepare **question → request → one result → one limitation**. Sharing is optional; no slides needed.

Local Jupyter: `python -m pip install -r requirements.txt`. Plotting optionally needs matplotlib.

[Attribution and provenance](SOURCES.md)
