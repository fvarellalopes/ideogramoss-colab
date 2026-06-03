# Ideogram 4 Colab Notebook

This Colab notebook runs [Ideogram 4](https://github.com/ideogram-oss/ideogram4) locally on a T4 GPU and exposes an image generation API through `cloudflared`.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/fvarellalopes/ideogramoss-colab/blob/main/Ideogram4_Colab.ipynb)

## How to use

1. Open the notebook using the button above (or directly in Colab).
2. Accept the model license on Hugging Face for `ideogram-ai/ideogram-4-nf4`.
3. Paste your `HF_TOKEN` in Colab Secrets (optional, but recommended).
4. Run the cells in order.
5. Copy the `cloudflared` tunnel URL shown at the end.

## Endpoint

Once the notebook is running, the API endpoint is:

- `POST {TUNNEL_URL}/generate`

Expected request body:

```json
{
  "prompt": "image description",
  "token": "YOUR_SECRET_TOKEN",
  "height": 1024,
  "width": 1024,
  "preset": "V4_TURBO_12",
  "seed": 1
}
```

Response format:

```json
{
  "image": "<base64 png>"
}
```

## Requirements

- T4 GPU or better.
- `HF_TOKEN` with access to the gated Ideogram 4 checkpoint.
- `IDEOGRAM_API_KEY` is required only if you want to use the default magic prompt.
