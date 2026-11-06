# Attribution and saved data

The guided search → video IDs → metadata → pandas workflow is adapted from the supplied teaching notebook attributed to Juan S. Gómez-Cruces. Juan’s notebook searched AfD-related channels, retrieved channel/video statistics, built a table and transcribed selected videos. This workshop keeps the collection sequence, removes audio/transcription and adds private key entry, error handling, bounded pagination, a saved-data fallback and open project templates. The comments route is an addition.

The AfD channel is a worked example, not a required research topic. Students can choose another public channel or a topic search.

The ten offline records were reconstructed from displayed saved outputs, not original raw API responses. Their exact observation time is unknown. Local title/date filtering does not reproduce YouTube’s search ranking. Detailed provenance is in `saved_video_records.json` and embedded in the notebooks.

Teaching inspiration: [Berkeley D-Lab](https://github.com/dlab-berkeley/Python-Web-APIs), [Katherine Walden](https://github.com/kwaldenphd/apis-python), and [Karsten T. Hansen / UCSD](https://bar.rady.ucsd.edu/CollectingDatawithAPI.html). Endpoint-specific behaviour is linked to current official documentation in [PARAMETERS.md](PARAMETERS.md).
