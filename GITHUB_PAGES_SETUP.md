# GitHub Pages + IONOS Domain Setup Guide

## Step 1: Create GitHub Repository

1. Go to https://github.com and sign in
2. Click the "+" icon → "New repository"
3. Repository name: `portfolio` (or `vaishnavi-kadam-portfolio`)
4. Make it **Public** (required for free GitHub Pages)
5. **Don't** initialize with README (we'll upload files)
6. Click "Create repository"

## Step 2: Upload Files to GitHub

### Option A: Using GitHub Desktop (Easiest)
1. Download GitHub Desktop: https://desktop.github.com
2. Install and sign in
3. File → Clone Repository → Select your new repository
4. Copy all files from `Website/` folder to the cloned repository folder
5. Commit and push

### Option B: Using Git Commands
```bash
cd "/Users/arayjadhav/Desktop/Vishu Job Applications/Website"
git init
git add .
git commit -m "Initial portfolio commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
git push -u origin main
```

### Option C: Using GitHub Web Interface
1. Go to your repository on GitHub
2. Click "uploading an existing file"
3. Drag and drop all files from `Website/` folder
4. Commit changes

## Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (top menu)
3. Scroll down to **Pages** (left sidebar)
4. Under "Source":
   - Select branch: `main` (or `master`)
   - Select folder: `/ (root)`
5. Click **Save**
6. Wait 1-2 minutes
7. Your site will be live at: `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME`

## Step 4: Connect IONOS Domain (DNS Option)

### In IONOS:
1. Go to your domain management
2. Click **DNS** option
3. You need to add these DNS records:

#### For Root Domain (vaishnavik.com):
Add **4 A Records**:
- **Type:** A
- **Name:** @ (or leave blank for root)
- **Value:** `185.199.108.153`
- **TTL:** 3600 (or default)

- **Type:** A
- **Name:** @
- **Value:** `185.199.109.153`
- **TTL:** 3600

- **Type:** A
- **Name:** @
- **Value:** `185.199.110.153`
- **TTL:** 3600

- **Type:** A
- **Name:** @
- **Value:** `185.199.111.153`
- **TTL:** 3600

#### For WWW Subdomain (www.vaishnavik.com):
Add **1 CNAME Record**:
- **Type:** CNAME
- **Name:** www
- **Value:** `YOUR_USERNAME.github.io` (replace with your GitHub username)
- **TTL:** 3600

### In GitHub:
1. Go to repository → **Settings** → **Pages**
2. Under "Custom domain", enter: `vaishnavik.com`
3. Check "Enforce HTTPS" (available after DNS propagates)
4. The `CNAME` file is already in your repository

## Step 5: Wait for DNS Propagation

- DNS changes can take 5 minutes to 48 hours
- Usually works within 1-2 hours
- Check status: https://www.whatsmydns.net/#A/vaishnavik.com

## Step 6: Verify

1. Visit `http://vaishnavik.com` (should redirect to HTTPS)
2. Visit `https://www.vaishnavik.com`
3. Both should show your portfolio

## Troubleshooting

**If domain doesn't work:**
- Wait longer for DNS propagation
- Verify DNS records in IONOS match exactly
- Check GitHub Pages settings show your domain
- Make sure `CNAME` file is in repository root

**If HTTPS doesn't work:**
- Wait 24 hours after DNS propagation
- Then enable "Enforce HTTPS" in GitHub Pages settings
