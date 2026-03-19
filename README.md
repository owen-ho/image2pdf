# Image to PDF Converter

A small web app I built for one reason: I was tired of saving images one by one and then manually adding them to Acrobat just to submit math and physics homework as a PDF.

I also kept forgetting which image belonged to which question, so this app lets me tag each image before export.

This app is privately hosted on my home server.

## Why this exists

- Faster homework submission workflow
- Keep image order in one place
- Add per-image tags so question mapping is obvious
- Avoid uploading homework images to third-party converters

## Features

- Drag and drop image upload
- Click to browse upload
- Paste images from clipboard
- Reorder-by-removal flow with numbered image cards
- Optional per-image tags
- Export all selected images into one PDF
- Custom output filename
- Advanced export options (optional panel)
- Export diagnostics to troubleshoot blur and quality issues

## Privacy

All conversion happens in your browser using jsPDF. Your images are not sent to an external API by this app.

## Tech stack

- Single-page HTML app (`index.html`)
- jsPDF (CDN)
- Nginx container for static hosting
- Docker + Docker Compose for deployment

## Run locally with Docker Compose

```bash
docker compose up --build -d
```

Open:

- http://localhost:8080

Stop:

```bash
docker compose down
```

## Project structure

- `index.html`: UI, upload flow, tagging, PDF generation, quality controls
- `Dockerfile`: Nginx container for serving the app
- `docker-compose.yml`: Local/home-server deployment config

## Typical workflow

1. Add images (drag/drop, browse, or paste).
2. Add tags like `Q1`, `Q2`, `Q3` so you do not lose track.
3. Keep defaults for quick export, or open **Advanced Options** for quality tuning.
4. Generate PDF and submit.

## Notes

- If output looks blurry, open **Advanced Options** and check export diagnostics.
- For sharper output, avoid upscaling and compare JPEG vs PNG modes.
