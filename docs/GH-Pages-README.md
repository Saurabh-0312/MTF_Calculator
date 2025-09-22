MTF Calculator - GitHub Pages Deployment Checklist

Quick checklist to ensure `MTF_Calculator.html` renders correctly on GitHub Pages:

1. Files in the repository root or `docs/` folder:

   - GitHub Pages can serve from the repository root or the `docs/` folder.
   - Place `MTF_Calculator.html` at the repository root or in `docs/` and select the same folder in repository settings.

2. No local file links:

   - Avoid file:// or absolute local drive paths (e.g., E:\\...). Use relative paths.

3. External assets:

   - This project uses Tailwind via CDN (https://cdn.tailwindcss.com). That's fine.
   - Ensure external fonts (Google Fonts) use HTTPS.

4. Case sensitivity:

   - GitHub Pages runs on Linux: filenames are case-sensitive. Ensure exact casing for filenames.

5. Root index.html:

   - Browsers open `index.html` by default. I created `index.html` that redirects to `MTF_Calculator.html` so visiting the repo root loads the calculator.

6. Test locally over HTTP:

   - Run a simple static server (Python 3):

     python -m http.server 8000

   - Or using Node's serve package:

     npx serve -s . -l 8000

   - Open http://localhost:8000/ to verify.

7. Commits & GitHub Pages settings:

   - Commit and push changes.
   - In GitHub -> Settings -> Pages: pick branch `main` (or `master`) and folder `/ (root)` or `/docs` depending where files are.

8. Console errors:

   - If the page looks broken, open browser devtools (Console) and check for 404s or blocked mixed-content errors.

9. Common fixes:
   - Ensure labels and tags are valid HTML. I've fixed malformed label tags in `MTF_Calculator.html`.
   - If fonts or scripts fail to load, try removing or hosting them locally.

If you'd like, I can prepare a commit for you and give the exact commands to run in PowerShell to push to GitHub, or I can keep iterating on layout or add a small deploy action.
