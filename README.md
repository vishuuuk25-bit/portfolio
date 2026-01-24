# Vaishnavi Kadam - Portfolio Website

Aerospace + Sustainability Engineering Portfolio

## Deployment on GitHub Pages

This portfolio is ready to deploy on GitHub Pages with custom domain support.

### Quick Setup

1. Create a new GitHub repository (name it something like `portfolio` or `vaishnavi-kadam-portfolio`)
2. Upload all files from this folder to the repository
3. Go to Settings → Pages
4. Select source branch (usually `main` or `master`)
5. Your site will be live at `https://yourusername.github.io/repository-name`

### Custom Domain Setup

1. In GitHub Pages settings, add your custom domain (e.g., `vaishnavikadam.com`)
2. In IONOS DNS settings, add these records:
   - Type: `A` records
     - Name: `@` → Value: `185.199.108.153`
     - Name: `@` → Value: `185.199.109.153`
     - Name: `@` → Value: `185.199.110.153`
     - Name: `@` → Value: `185.199.111.153`
   - Type: `CNAME` record
     - Name: `www` → Value: `yourusername.github.io`
3. Wait for DNS propagation (can take up to 48 hours, usually much faster)
4. Enable "Enforce HTTPS" in GitHub Pages settings

## Files Structure

```
/
├── index.html          # Main page
├── styles.css          # Stylesheet
├── images/             # All images
│   ├── Profile_Photo.jpg
│   ├── Aircraft.jpg
│   ├── VTOl.jpg
│   ├── Project_1.jpeg
│   └── Project_1a.jpeg
└── README.md           # This file
```

## Local Development

Simply open `index.html` in a browser or use a local server:

```bash
cd Website
python3 -m http.server 8000
```

Then visit `http://localhost:8000`
