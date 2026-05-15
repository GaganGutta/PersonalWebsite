# gagan.cc

Personal site. Static HTML, no build step. Deployed on Vercel.

## Local preview

Just open `index.html` in a browser, or run a tiny server:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy

### 1. Push to GitHub

Create an empty repo on github.com (no README, no gitignore), then:

```bash
git init
git add .
git commit -m "initial site"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

### 2. Deploy to Vercel

**Dashboard route (easiest):**

1. vercel.com → sign in with GitHub
2. Add New → Project → pick the repo
3. Framework Preset: **Other**
4. Deploy

**CLI route:**

```bash
npm i -g vercel
vercel
vercel --prod
```

Every `git push` to `main` will redeploy automatically.

### 3. Custom domain

Vercel dashboard → project → Settings → Domains → add your domain and point DNS at the records Vercel gives you.

## Adding images

Drop image files into a `photos/` folder, then replace any placeholder div like:

```html
<div class="img-ph img-wide" data-label="Photo 01"></div>
```

with:

```html
<div class="img-ph img-wide"><img src="photos/whatever.jpg" alt=""></div>
```

The label and grid background disappear automatically once an `<img>` is inside.

Aspect ratio classes: `img-portrait` (4:5), `img-square`, `img-wide` (16:10), `img-tall` (3:4).
