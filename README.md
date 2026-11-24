# Codemiq Web (codemiq.mhr.bd)

Official landing website, developer showcase, and policy portal for **Codemiq** (MIYAJI TRADERS).

## 🚀 Overview
- **Domain:** `https://codemiq.mhr.bd`
- **Framework:** Astro 5.x + Tailwind CSS v4 (Zero-JS static HTML, ultra-fast load time)
- **Features:**
  - Official Organization Showcase (Miyaji Traders, D-U-N-S: `732333260`, Trade License: `179`)
  - **bdHousing** Mobile App Showcase with Screenshots & direct APK download (`/downloads/bdhousing-release.apk`)
  - Google Play Compliant **Privacy Policy** (`/privacy`)
  - Terms of Service (`/terms`)
  - Google Play Compliant **User Data & Account Deletion Request** (`/delete-account`)
  - Office contact details (Babul Market, Sadar, Noakhali)
- **Deployment:** Dokploy (Docker / Nginx multi-stage build)

---

## 🛠️ Local Development
```bash
# Install dependencies
npm install

# Start local development server
npm run dev

# Build production static bundle
npm run build

# Preview build locally
npm run preview
```

---

## 🐳 Dokploy Deployment Guide

### Option 1: Git Repository (Recommended)
1. Push this repository to your GitHub/GitLab:
   ```bash
   git remote add origin <YOUR_GITHUB_REPO_URL>
   git branch -M main
   git push -u origin main
   ```
2. Log in to your **Dokploy** Dashboard on your VPS.
3. Click **Create Application**.
4. Select **GitHub** or **Git** and choose this repository (`main` branch).
5. Set Build Type to **Dockerfile** (it will automatically use the included `Dockerfile` and `nginx.conf`).
6. Set the Domain in Dokploy:
   - Domain: `codemiq.mhr.bd`
   - Enable **HTTPS (Let's Encrypt)**
7. Click **Deploy**!

### Option 2: Dockerfile / Standalone Docker
```bash
docker build -t codemiq-web .
docker run -d -p 80:80 codemiq-web
```

---

## 🔍 Google Search Console & Play Console Verification
1. Once deployed, open [Google Search Console](https://search.google.com/search-console).
2. Add Property: `https://codemiq.mhr.bd`.
3. If Google gives an HTML verification file (e.g. `google12345.html`), place it inside `/public/` and deploy, or add the meta tag to `src/layouts/Layout.astro`.
4. Return to [Google Play Console](https://play.google.com/console) $\to$ **Verify your organization's website** $\to$ enter `https://codemiq.mhr.bd` $\to$ Instant verification!
