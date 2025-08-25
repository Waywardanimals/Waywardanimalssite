# Mayhem's Home for Wayward Animals Website

Always reference these instructions first and fallback to search or bash commands only when you encounter unexpected information that does not match the info here.

## Working Effectively

### Bootstrap and Setup
- **NEVER CANCEL**: No build process required - setup takes < 5 seconds
- Run `cd /path/to/repository` to navigate to the project root
- Install HTML validation tool: `npm install -g html-validate` -- takes 10 seconds, NEVER CANCEL
- Verify Node.js available: `node --version && npm --version`

### Development Server
- **NEVER CANCEL**: Server starts in < 3 seconds
- Start development server: `python3 -m http.server 8000 --directory .`
- Website accessible at: `http://localhost:8000/`
- Stop server: `pkill -f "python3 -m http.server"` or Ctrl+C

### Validation and Testing
- **NEVER CANCEL**: HTML validation takes < 5 seconds
- Validate HTML: `html-validate index.html`
- Expected: 31 validation warnings about inline styles and unescaped ampersands - these are acceptable for this project
- Test HTTP response: `curl -s -o /dev/null -w "%{http_code}" http://localhost:8000/` (should return 200)
- **NEVER CANCEL**: Manual testing takes < 2 minutes

## Validation Scenarios

### Manual Testing Requirements
Always test these scenarios after making changes:

1. **Website Loading**: Navigate to `http://localhost:8000/` and verify page loads with title "Mayhem's Home for Wayward Animals"
2. **Chief Mayhem Navigator**: Click the Chief Mayhem Navigator image to open/close the menu bubble
3. **Anchor Navigation**: Click "Adopt a Sidekick" button to navigate to #adopt section
4. **Section Navigation**: Verify anchor links work for #adopt, #fund, #stories sections
5. **External Links**: Verify external links point to correct URLs (adoptapet.com, square.link, shopify.com)
6. **Responsive Design**: Test page on different screen sizes
7. **Images**: Verify all images in assets/ directory load correctly

### Expected Validation Results
- `html-validate index.html` will show 31 errors about inline styles and unescaped ampersands
- These validation errors are acceptable - the website uses inline styles intentionally for simplicity
- All external links should be functional (adoption links, donation links, merchandise)

## Common Tasks

### Repository Structure
```
.
├── .github/
│   └── copilot-instructions.md
├── assets/
│   ├── chaos-heroine-poster.jpg
│   ├── logo-mayhems-home.jpg
│   ├── Chief-Mayhem.jpg
│   ├── Chaos-Hero-Illustration.jpg (empty)
│   └── Mayhem-Logo.jpg (empty)
├── index.html
└── .git/
```

### Key Files and Sections
- **index.html**: Single-page website with embedded CSS and JavaScript
- **assets/**: Image directory with comic-style illustrations
- **No build process**: Static HTML website requires no compilation
- **No dependencies**: No package.json, node_modules, or external build tools required

### Website Content Sections
1. Hero section with Chief Mayhem Navigator interactive menu
2. Rescue Stories (Wiley, Katie, Alder & Douglas)
3. Fix-It Fund fundraiser with progress bar
4. Adoptables section with external links
5. Footer with social media links

### Making Changes
- Edit `index.html` directly for content changes
- CSS is embedded in `<style>` tags in the `<head>` section
- JavaScript is embedded in `<script>` tags before closing `</body>`
- No compilation or build step required
- Test changes immediately by refreshing browser

### Missing Files
- `about.html` is referenced in navigation but does not exist (returns 404)
- This is intentional - about page not yet implemented

### External Dependencies
- Google Fonts (fonts.googleapis.com) for Bangers, Luckiest Guy, and Raleway fonts
- May fail to load in some environments but website remains functional

## Timing Expectations
- **Server startup**: < 3 seconds - NEVER CANCEL
- **HTML validation**: < 5 seconds - NEVER CANCEL  
- **Manual testing**: < 2 minutes per scenario - NEVER CANCEL
- **No build process**: Changes are immediate, no compilation required

## Important Notes
- This is a static HTML website for an animal rescue organization
- Uses comic book aesthetic with purple, magenta, and yellow color scheme
- Interactive element: Chief Mayhem Navigator image shows/hides menu on click
- Website is production-ready as-is, requires only static file hosting
- No database, backend, or server-side processing required

## Troubleshooting
- If images don't load: Verify files exist in assets/ directory
- If validation shows errors: Expected 31 warnings about inline styles are acceptable
- If external links fail: Check network connectivity, links may be temporary
- If server won't start: Ensure port 8000 is available or use different port: `python3 -m http.server 8001`