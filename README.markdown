# PrintVis

PrintVis is a web-based tool designed to help yearbook students and educators visualize and create two-page yearbook spreads (17" x 11", two 8.5" x 11" pages side by side). It emphasizes a four-module "bullseye" design approach, where students can drag crosshairs to define four quadrants, add content to each module using a toolbar, and restructure the layout by dragging elements. Elements are tiled left to right, top to bottom within each quadrant, constrained to its boundaries, with a title and page number/label (e.g., “Page 1 - Senior Events”) anchoring the design. The spread can be exported as a landscape PDF. Built with an intuitive interface, PrintVis is ideal for high school yearbook classes.

## Features
- **Two-Page Spread**: Visualize a 17" x 11" layout (two 8.5" x 11" pages) on a scalable canvas.
- **Bullseye Crosshairs**: Click to select a crosshair (vertical or horizontal), move with the mouse, click again to place, dividing the spread into four quadrants.
- **Module Selection**: Click a quadrant to select it (highlighted with a blue border) and display a toolbar.
- **Toolbar**: Appears when a module is selected, with icons to add:
  - **Title**: Large, bold text (e.g., “Title”).
  - **Copy**: Body text (e.g., sample paragraph).
  - **Photo**: Placeholder image (planned: uploadable).
  - **Caption**: Small text below photos.
  - **Shape**: Rectangle placeholder (planned: customizable shapes/colors).
- **Element Tiling**: Elements are added to the selected quadrant, tiled left to right, top to bottom in a grid (150px x 100px boxes), constrained to the quadrant’s boundaries.
- **Drag-and-Drop Restructuring**: Click and drag elements within a quadrant to new grid positions, snapping to the 150px x 100px grid, with yellow outline feedback during drag.
- **Four Modules**: Each quadrant supports multiple elements, with placeholders if empty.
- **Title Element**: A prominent title placeholder on the spread (planned: editable).
- **Page Number and Label**: Fixed in the lower-left corner (e.g., “Page 1 - Senior Events”).
- **PDF Export**: Export the spread as a 17" x 11" landscape PDF via a LaTeX file, including all canvas content (pages, crosshairs, elements, text).
- **Sidebar Tools**: Placeholder buttons for adding text, uploading photos, adding shapes, editing titles, exporting designs, and exporting PDF.
- **Responsive Design**: Mobile-friendly interface with a collapsible sidebar and adaptive toolbar for classroom use.
- **Earthy Aesthetic**: Clean, modern look with greens, browns, and blues, inspired by natural tones.

*Note*: PrintVis is a prototype. Features like text editing, photo uploads, shape customization, and direct PDF rendering are planned for future updates. Console warnings about React DevTools, Tailwind CSS CDN, and Babel are expected in development and do not affect functionality, making the app suitable for classroom use on GitHub Pages.

## Usage
1. Open PrintVis in a browser (e.g., visit `https://kappter.github.io/PrintVis/` or run locally; see Installation).
2. Explore the 17" x 11" spread canvas, showing two 8.5" x 11" pages side by side.
3. Adjust crosshairs:
   - Click the red vertical or horizontal line to select it.
   - Move the mouse to position the line.
   - Click again to place the line, dividing the spread into four quadrants.
4. Click a quadrant to select it (a blue border appears) and display the toolbar.
5. Use the toolbar icons to add elements to the selected quadrant:
   - **T**: Add a title.
   - **C**: Add body text (copy).
   - **P**: Add a photo placeholder.
   - **Cp**: Add a caption.
   - **S**: Add a shape placeholder.
6. View added elements, which tile left to right, top to bottom in the quadrant (150px x 100px boxes). Elements stop adding if the quadrant is full.
7. Restructure layout:
   - Click and drag an element within its quadrant (yellow outline appears).
   - Move to a new grid position, release to place (snaps to 150px x 100px grid).
   - Elements cannot overlap or move outside the quadrant.
8. Export the spread:
   - Click “Export PDF” in the sidebar to download `spread.tex`.
   - Compile the LaTeX file using `latexmk` (e.g., `latexmk -pdf spread.tex`) or upload to Overleaf to generate a 17" x 11" landscape PDF.
9. Check the spread title (“Spread Title”) and page number/label (“Page 1 - Senior Events”) in the lower-left corner.
10. Explore the sidebar tools (currently placeholders for future functionality except PDF export).
11. Test on mobile devices to ensure the sidebar collapses, the toolbar adapts, and the canvas scales properly.

*Note*: Console warnings about React DevTools, Tailwind CSS CDN, and Babel are normal for development, do not affect student use, and can be ignored for classroom prototyping. If a quadrant is too small to add elements or an element cannot be moved due to overlap, a console warning appears (future: UI alert).

*Planned*: Edit text, upload photos, customize shapes, direct PDF rendering, UI alerts for layout issues.

## Installation (for Development)
1. Clone the repository:
   ```bash
   git clone https://github.com/kappter/PrintVis.git
   ```
2. Navigate to the project directory:
   ```bash
   cd PrintVis
   ```
3. Serve the project locally:
   ```bash
   python -m http.server 8000
   ```
4. Open `http://localhost:8000` in your browser to view PrintVis.

*Note*: PrintVis uses CDN-hosted React, Babel, and Tailwind CSS, requiring an internet connection for the prototype. For production or classroom deployment, consider the Production Setup.

## Deployment on GitHub Pages
PrintVis is designed to work seamlessly on GitHub Pages for classroom use. To deploy:
1. Push files to your GitHub repository:
   ```bash
   git add index.html styles.css favicon.ico README.md
   git commit -m "Fix Babel SyntaxError for drag-and-drop"
   git push origin main
   ```
2. Enable GitHub Pages in repository settings:
   - Go to **Settings** > **Pages**.
   - Set **Source** to `main` branch and `/ (root)` folder.
   - Save and wait 1–5 minutes for deployment.
3. Access the app at `https://kappter.github.io/PrintVis/`.
4. Update this README with the live URL and repository link.

*Troubleshooting*:
- **Blank Page**:
  - Ensure `index.html`, `styles.css`, and `favicon.ico` are in the root of the `main` branch, and the repository is public.
  - Verify GitHub Pages is set to `main`/`/ (root)` in **Settings** > **Pages**.
  - Confirm `index.html` uses `ReactDOM.createRoot` and compatible JS (e.g., no optional chaining `?.`).
  - Test locally (`python -m http.server 8000`) to isolate deployment issues.
  - Look for logs like `Babel script loaded`, `App rendering`, `SpreadCanvas rendering`, `Sidebar rendering`.
  - If errors appear in the error boundary (e.g., “Something went wrong”), share the message.
- **Babel SyntaxError**:
  - Check console for errors like `Unexpected token` in `babel.min.js`.
  - Verify `index.html` avoids modern JS (e.g., `draggingElement && draggingElement.module` instead of `draggingElement?.module` in `useEffect`).
  - If persistent, share full error stack.
- **404 Errors**:
  - Confirm `styles.css` and `favicon.ico` are correctly named (case-sensitive, e.g., `styles.css` not `Styles.css`) and in the root.
  - Inspect the Network tab (F12) for failed requests.
- **CDN Issues**:
  - Verify CDNs (`jsdelivr.net`, `unpkg.com`, `cdn.tailwindcss.com`) are not blocked by your network (e.g., school firewall).
  - Test locally to confirm CDN access.
  - Use Production Setup if blocked.
- **Rendering Issues**:
  - Check console for `ErrorBoundary caught`, `Canvas element not found`, or `modules` state logs.
  - Add `console.log('Root element:', document.getElementById('root'))` before `ReactDOM.createRoot` to verify DOM.
  - Share console logs or errors for debugging.
- **Crosshair Issues**:
  - If crosshairs don’t toggle (click to select, click to place), check console for `Started dragging` and `Stopped dragging` logs.
  - Ensure `handleMouseDown` toggles `dragging` state correctly.
- **Element Tiling Issues**:
  - If elements don’t tile correctly, check console for `Adding element` logs with `col`, `row`.
  - Verify quadrant boundaries in `addElement` (e.g., `maxCols`, height check).
  - If elements don’t appear, ensure `modules` state updates in `useEffect`.
- **Drag-and-Drop Issues**:
  - If elements don’t drag, check console for `Started dragging element` and `Moved element` logs.
  - Verify `handleCanvasMouseDown` detects element clicks.
  - If elements overlap or move outside quadrant, check boundary checks in `handleMouseUp`.
- **PDF Export Issues**:
  - If `spread.tex` doesn’t download, check console for `Exported LaTeX file`.
  - If PDF compilation fails, verify LaTeX code syntax and compile with `latexmk` or Overleaf.
  - Share compilation errors for debugging.

*Note*: Console warnings are safe for prototyping and hidden from students. Ensure CDN URLs are accessible.

## Production Setup
To prepare PrintVis for long-term classroom use (e.g., hosting on GitHub Pages without CDN warnings):
1. **Install Tailwind CSS Locally**:
   - Initialize a Node.js project:
     ```bash
     npm init -y
     npm install -D tailwindcss
     npx tailwindcss init
     ```
   - Create `input.css`:
     ```css
     @tailwind base;
     @tailwind components;
     @tailwind utilities;
     ```
   - Update `tailwind.config.js`:
     ```js
     module.exports = {
       content: ['./*.html'],
       theme: { extend: {} },
       plugins: [],
     };
     ```
   - Build CSS:
     ```bash
     npx tailwindcss -i ./input.css -o ./styles.css
     ```
   - Replace `<script src="https://cdn.tailwindcss.com"></script>` in `index.html` with `<link rel="stylesheet" href="styles.css">`.
2. **Use Production React**:
   - Replace development React scripts with production versions:
     ```html
     <script src="https://cdn.jsdelivr.net/npm/react@18.2.0/umd/react.production.min.js"></script>
     <script src="https://cdn.jsdelivr.net/npm/react-dom@18.2.0/umd/react-dom.production.min.js"></script>
     ```
   - This removes the React DevTools warning.
3. **Precompile Babel**:
   - Use a build tool (e.g., Vite) to precompile JSX, removing the Babel CDN and warning.
4. **Host on GitHub Pages**:
   - Commit and push updated files.
   - Verify the app at `https://kappter.github.io/PrintVis/` with no console warnings.

## Contributing
We welcome feedback and contributions from students, educators, and developers! To contribute:
1. Fork the repository on GitHub.
2. Create a new branch for your feature or fix (e.g., `git checkout -b feature/photo-upload`).
3. Commit your changes (e.g., `git commit -m "Add photo upload functionality"`).
4. Push to your fork (e.g., `git push origin feature/photo-upload`).
5. Open a pull request on the [PrintVis GitHub repository](https://github.com/kappter/PrintVis).

Suggestions for new features (e.g., text editing, templates, undo/redo) are encouraged! Submit ideas via GitHub Issues.

## License
© 2025 Ken Kapptie. For educational use only. All rights reserved.