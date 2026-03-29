# Sheeot Landing Page

Minimal static landing page for [sheeot.com](https://sheeot.com). This is a placeholder site intended to be updated by a designer.

## Structure

Single-page static site — just `index.html`, no build tools or dependencies.

## Hosting on GitHub Pages with a Custom Domain

### 1. Create a GitHub repository

```bash
cd /path/to/this/directory
git init
git add .
git commit -m "Initial landing page"
git remote add origin git@github.com:sheeot-studio/landing.git
git branch -M main
git push -u origin main
```

### 2. Enable GitHub Pages

1. Go to the repo on GitHub → **Settings** → **Pages**
2. Under **Source**, select **Deploy from a branch**
3. Set branch to `main` and folder to `/ (root)`
4. Click **Save**

### 3. Configure custom domain

1. In **Settings** → **Pages** → **Custom domain**, enter your domain (e.g. `sheeot.com` or `www.sheeot.com`)
2. Click **Save**
3. Optionally check **Enforce HTTPS**

### 4. DNS setup (at your domain registrar)

For an apex domain (`sheeot.com`), add **A records** pointing to GitHub's IPs:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

For a `www` subdomain, add a **CNAME record**:

```
www  →  sheeot-studio.github.io
```

### 5. Add a CNAME file

Create a `CNAME` file in the repo root with your domain:

```bash
echo "sheeot.com" > CNAME
git add CNAME
git commit -m "Add CNAME for custom domain"
git push
```

> DNS changes can take up to 24-48 hours to propagate. GitHub will automatically provision an SSL certificate once DNS is verified.

## Updating

Edit `index.html` directly — no build step needed. Push to `main` and GitHub Pages will deploy automatically.
