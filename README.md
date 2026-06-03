# Ideogram 4 Colab

Notebook Colab para rodar o modelo [Ideogram 4](https://github.com/ideogram-oss/ideogram4) localmente com GPU T4 e expor uma API geradora de imagens via `cloudflared`.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/fvarellalopes/ideogramoss-colab/blob/main/Ideogram4_Colab.ipynb)

## Como usar

1. Abra pelo botão acima (ou diretamente no Colab).
2. Aceite a licença no Hugging Face em `ideogram-ai/ideogram-4-nf4`.
3. Cole seu `HF_TOKEN` no Colab Secrets como `HF_TOKEN` (opcional, mas recomendado).
4. Rode as células em ordem.
5. Copie a URL do `cloudflared` exibida no final.

## Endpoint

Depois que o notebook rodar, o endpoint é:

- `POST {TUNNEL_URL}/generate`

Body esperado:

```json
{
  "prompt": "descrição da imagem",
  "token": "YOUR_SECRET_TOKEN",
  "height": 1024,
  "width": 1024,
  "preset": "V4_TURBO_12",
  "seed": 1
}
```

A resposta retorna `{"image": "<base64 png>"}`.

## Pré-requisitos

- GPU T4 ou superior.
- `HF_TOKEN` com acesso ao checkpoint gated do Ideogram 4.
- `IDEOGRAM_API_KEY` é necessário apenas se quiser usar o magic prompt padrão.
