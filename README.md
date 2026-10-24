# Arun's Rebuild Fund – website

Files:

- `index.html`: the public fundraiser page
- `data.json`: all the content (amounts, UPI, updates, videos, needs list)
- `admin.html`: your private editor for `data.json`
- `images/`: put the photos here (see below)

## 1. Add the photos

Put these three files in the `images` folder, with exactly these names:

| File | What |
|---|---|
| `images/family.jpg` | Family photo (landscape works best) |
| `images/arun.jpg` | Arun's photo with his ID card (portrait) |
| `images/upi-qr.png` | Screenshot of his UPI QR code, cropped to just the QR |

Resize photos to around 1200px wide so the page loads fast on mobile data. If a photo is missing, the page simply hides that spot.

Before uploading, blur the employee number and any barcode on the ID card.

## 2. Fill in the placeholders

Open `data.json` and replace everything in [square brackets]. Or do it later from `admin.html` once the site is live.

## 3. Put the site on GitHub

1. Go to github.com → New repository → name it `arun-fund` → Private or Public (either works) → Create.
2. Click "uploading an existing file" and drag in everything in this folder, including the `images` folder. Commit.

## 4. Connect Netlify

1. app.netlify.com → Add new site → Import an existing project → GitHub → pick `arun-fund`.
2. Leave the build command empty and the publish directory as `/` (or blank). Deploy.
3. Site configuration → Change site name → the site is `fundraise-for-arun`, so the link is `https://fundraise-for-arun.netlify.app`.

Every time `data.json` changes on GitHub, Netlify republishes automatically in under a minute.

## 5. Set up admin access

The admin page saves to GitHub using a personal access token that only you hold.

1. GitHub → Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token.
2. Repository access: Only select repositories → `arun-fund`.
3. Permissions → Repository permissions → Contents: Read and write. Nothing else.
4. Expiration: 30 or 60 days (the length of the drive).
5. Copy the token.
6. Open `https://<your-site>.netlify.app/admin.html`, enter your GitHub username, `arun-fund`, `main`, and the token, then press Connect and load.

The token stays in that browser only. It is never part of the website, so visitors can open admin.html but can't change anything without a token. Use "Forget token" on shared computers, and delete the token on GitHub when the drive ends.

## Updating

Open `/admin.html` on your phone or laptop, change the total, donor count, updates, needs or videos, and press **Save to site**.

If you ever can't use the admin page: edit `data.json` directly on github.com (pencil icon → Commit). Same result.
