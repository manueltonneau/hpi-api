# Setup

## Open the code

[Open Colab](https://colab.research.google.com/github/manueltonneau/hpi-api/blob/main/api_workshop.ipynb) → **File → Save a copy in Drive**. If imports fail: `%pip install pandas requests`.

## Create an API key

1. Open [Google Cloud](https://console.cloud.google.com/) → project selector → **New project**. Create and select it.
2. **APIs & Services → Library → YouTube Data API v3 → Enable**.
3. **Credentials → Create credentials → API key**.
4. Under **API restrictions**, select **YouTube Data API v3**. Leave service-account authentication unchecked, then create/save. If the key was created immediately, open its details to apply the restriction.

Use a standard API key, not OAuth or a service-account key. Restrictions must suit Python/Colab; a browser-referrer restriction can block these calls. [Official instructions](https://developers.google.com/youtube/data/getting-started) · [Key settings](https://docs.cloud.google.com/docs/authentication/api-keys)

## Run

Set `OFFLINE=False` in the first cell and enter your key in the **hidden prompt**. Keep keys out of shared code and outputs. Run cells in order; restart and rerun if switching modes.

## If blocked

- **No key / account restriction:** use `OFFLINE=True` or work in pairs.
- **403:** check the error reason, enabled API, key restrictions and quota.
- **Comments disabled:** choose another video or project.
- **Save:** download CSV/manifest from `workshop_outputs/` in Colab’s file browser.
