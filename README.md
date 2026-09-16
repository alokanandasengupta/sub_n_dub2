# Auto Subtitle Generator (Whisper)

A Gradio app that turns an audio or video file into subtitles, using
`faster-whisper` (the `large-v3-turbo` CT2 model) for transcription. Upload
a file, pick a language (or auto-detect), and get back four subtitle
flavors from one pass — no manual timestamping.

## Outputs

- **Default SRT** — standard sentence-level subtitles
- **Customized SRT** — subtitle lines split on a configurable max
  words-per-segment, tuned for vertical/short-form video
- **Word-level SRT** — one subtitle entry per word, for karaoke-style
  captioning
- **Shorts SRT** — a variant tuned for short-form platforms
- **Plain text transcript**

## Running it

```bash
pip install -r requirements.txt
# packages.txt lists the one system dependency: ffmpeg
python backend.py
```

Launches a Gradio interface (add `--share` for a public link, `--debug`
for verbose logs).

## Stack

`faster-whisper` (CTranslate2-optimized Whisper), Gradio, PyTorch/torchaudio.
