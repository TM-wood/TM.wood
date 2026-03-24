# T.M.wood - Handcrafted Design & Woodwork Portfolio

A modern, interactive portfolio website for T.M.wood, built with clean HTML, CSS, and vanilla JavaScript.

## Features

- **Responsive Design**: Beautiful on all devices (mobile, tablet, desktop)
- **Interactive Quote Form**: Multiple-choice questionnaire that doesn't require lengthy paragraphs
- **Project Timeline**: Visual representation of the process from discovery to completion
- **Portfolio Showcase**: Project-based layout with detailed case studies
- **Performance Optimized**: Fast loading with minimal dependencies
- **No Backend Required**: Runs entirely on GitHub Pages

## File Structure

```
├── index.html          # Main homepage
├── portfolio.html      # Full portfolio with project case studies
├── quote.html          # Interactive quote request form
└── README.md           # This file
```

## Setup Instructions

### Option 1: GitHub Pages (Recommended - Free Hosting)

1. **Create a GitHub Repository**
   - Go to github.com and create a new public repository
   - Name it `yourusername.github.io` OR any name you prefer

2. **Upload the Files**
   - Upload `index.html`, `portfolio.html`, and `quote.html` to your repository
   - You can do this via:
     - GitHub's web interface (drag & drop)
     - Git command line: 
       ```
       git clone https://github.com/yourusername/your-repo.git
       cd your-repo
       # Copy the HTML files here
       git add .
       git commit -m "Initial commit"
       git push
       ```

3. **Enable GitHub Pages**
   - Go to Settings → Pages
   - Select "Deploy from a branch"
   - Choose the branch (usually `main`) and `/root` folder
   - Wait for the site to build (usually 1-2 minutes)
   - Your site will be live at `https://yourusername.github.io` or `https://yourusername.github.io/your-repo`

4. **Optional: Connect Custom Domain**
   - In Settings → Pages, add your custom domain
   - Update your domain's DNS settings to point to GitHub Pages

### Option 2: Other Hosting (Netlify, Vercel, etc.)

If you prefer alternatives:

- **Netlify**: Drag & drop your files to netlify.com
- **Vercel**: Connect your GitHub repo at vercel.com
- **Traditional Hosting**: Upload files via FTP to any web host

## Customization Guide

### Update Your Name & Business Info

1. **In index.html**:
   - Change `<a href="#" class="logo">T.M.wood</a>` to your business name
   - Update `<title>T.M.wood - Handcrafted Design & Woodwork</title>`
   - Update hero text and descriptions
   - Replace footer copyright year if needed

2. **In portfolio.html** and **quote.html**:
   - Same changes for logo and title tags
   - Update footer information

### Replace Placeholder Images

The site uses placeholder images from Unsplash. Replace them with your own:

1. In `index.html`, find lines like:
   ```html
   <img src="https://images.unsplash.com/photo-1495474472645-4c71bcdd2d18?w=800&h=600&fit=crop" alt="Work 1">
   ```

2. Replace the URL with your own image:
   ```html
   <img src="images/your-image.jpg" alt="Your Work">
   ```

3. Best practices:
   - Use `.jpg` or `.webp` for photos (better compression)
   - Keep image file sizes under 500KB per image
   - Use descriptive alt text

### Update Project Information

In `portfolio.html`, update each project section:

```html
<h2 class="project-title">Your Project Name</h2>
<div class="project-meta">
    <div class="project-meta-item"><strong>Client:</strong> Client Name</div>
    <div class="project-meta-item"><strong>Year:</strong> 2024</div>
    <div class="project-meta-item"><strong>Materials:</strong> Wood types</div>
</div>
<p class="project-description">Your project description...</p>
```

### Modify Colors & Styling

The design uses CSS variables. To customize colors, edit the `:root` section in any HTML file:

```css
:root {
    --primary-dark: #1a1a1a;      /* Dark backgrounds */
    --primary-light: #f5f5f0;      /* Light backgrounds */
    --accent: #a67c52;             /* Brand accent color (brownish) */
    --accent-light: #d4af85;       /* Lighter accent color */
    --text-dark: #2a2a2a;          /* Dark text */
    --text-light: #666;            /* Gray text */
    --border-color: #e0e0e0;       /* Borders & separators */
}
```

Change the hex color codes to match your brand colors.

### Contact Information & Links

1. **Email Link**: In the footer and CTA sections, you can add a direct email link:
   ```html
   <a href="mailto:your-email@example.com">Get in Touch</a>
   ```

2. **Social Links**: Add social media in the footer by updating the footer section.

## Form Submissions (Quote Page)

The quote form uses browser localStorage to save submissions. This means:

- **No backend required** - Works on GitHub Pages
- Data is stored in visitor's browser
- To retrieve submissions, you can:
  1. **Add email integration** (requires a backend service like Formspree, Getform, or Firebase)
  2. **Check browser console** (inspect element → Application tab → Local Storage)

### Optional: Add Email Integration

To actually receive quote requests via email:

1. **Using Formspree** (easiest for beginners):
   - Go to formspree.io
   - Create a form and get your form endpoint
   - Replace the form action in `quote.html`:
     ```html
     <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
     ```

2. **Using Getform**:
   - Similar process at getform.io
   - Get your webhook URL
   - Modify the JavaScript to POST to their endpoint

3. **Custom Backend** (for developers):
   - Create a simple backend API
   - Update the form submission JavaScript

## Mobile Optimization

The site is fully responsive, but test it on your phone:
- Use Chrome DevTools (F12) → Toggle device toolbar
- Test on actual devices before launch
- Check form input sizes are touch-friendly (already done in this design)

## SEO Basics

1. **Update Meta Tags** in each HTML file:
   ```html
   <meta name="description" content="Your business description here">
   <meta name="keywords" content="woodworking, design, craftsmanship">
   ```

2. **Create a sitemap.xml** (optional but recommended):
   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
     <url>
       <loc>https://yourdomain.com/</loc>
       <lastmod>2024-03-25</lastmod>
     </url>
     <url>
       <loc>https://yourdomain.com/portfolio.html</loc>
       <lastmod>2024-03-25</lastmod>
     </url>
     <url>
       <loc>https://yourdomain.com/quote.html</loc>
       <lastmod>2024-03-25</lastmod>
     </url>
   </urlset>
   ```

3. **Add analytics** (optional):
   - Google Analytics: Add tracking code to `<head>` section

## Fonts

The site uses Google Fonts (free):
- **Cormorant Garamond**: Elegant serif for headings
- **Inter**: Clean sans-serif for body text

These are loaded from Google's CDN, so no installation needed.

## Browser Support

- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+
- Mobile browsers (iOS Safari, Chrome Mobile)

## Performance Tips

1. **Optimize Images**: Use tools like TinyPNG or ImageOptim
2. **Lazy Loading**: Add `loading="lazy"` to img tags (optional)
3. **Cache Busting**: Add version to CSS: `?v=1.0`

## Troubleshooting

### Site Not Loading
- Check that you've enabled GitHub Pages in Settings
- Verify file names are exactly: `index.html`, `portfolio.html`, `quote.html`
- Wait 5 minutes after first push - GitHub needs time to build

### Links Not Working
- Make sure all file names are lowercase
- Use relative paths: `portfolio.html` not `/portfolio.html`
- Check that HTML files are in the root directory

### Images Not Showing
- Verify image file extensions (case-sensitive on Linux/GitHub)
- Use relative paths: `images/photo.jpg` not absolute URLs
- Check file sizes aren't too large

### Styling Looks Off
- Clear browser cache (Ctrl+Shift+Delete)
- Check that CSS is in `<style>` tags within each HTML file

## License

This website is open source and free to use. Modify and customize as needed for your business.

---

**Need Help?**
- GitHub Pages Help: https://docs.github.com/en/pages
- HTML Reference: https://developer.mozilla.org/en-US/docs/Web/HTML
- CSS Guide: https://developer.mozilla.org/en-US/docs/Web/CSS

Happy building! 🚀
