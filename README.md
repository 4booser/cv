# CV — Oleksii Chepurniak

Three one-page CVs sharing one stylesheet.

```
index.html      landing page with links to all three
backend.html    Backend .NET
dotnet.html     Fullstack .NET / React
node.html       Fullstack Node.js / React
style.css       shared styles (screen + print)
cv-backend.pdf  generated from backend.html
cv-dotnet.pdf   generated from dotnet.html
cv-node.pdf     generated from node.html
```

## Editing

Edit the HTML, then regenerate the PDF:

```bash
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
  --headless --disable-gpu --no-pdf-header-footer \
  --print-to-pdf=cv-dotnet.pdf dotnet.html
```

Each sheet is a fixed A4 box (`210mm × 297mm`, `overflow: hidden`), so anything past
the bottom edge is silently cut. After editing, always check the PDF is still 1 page
and the last line is intact:

```bash
pdfinfo cv-dotnet.pdf | grep Pages
```

## Deploy — GitHub Pages (free)

```bash
git init
git add .
git commit -m "CV"
git branch -M main
git remote add origin git@github.com:4booser/cv.git
git push -u origin main
```

Then on GitHub: **Settings → Pages → Source: Deploy from a branch → main / (root) → Save**.

Live in about a minute at `https://4booser.github.io/cv/`.

Every later `git push` republishes automatically.
