# PrintVis

PrintVis is a web-based tool designed to help yearbook students and educators visualize and create two-page yearbook spreads (17" x 11", two 8.5" x 11" pages side by side). It emphasizes a four-module "bullseye" design approach, where students can drag crosshairs to define the intersection of four quadrants and add content to each module using a toolbar. Each module can contain text, photo, and shape elements, with a title and a page number/label (e.g., “Page 1 - Senior Events”) anchoring the design. Built with a simple, intuitive interface, PrintVis bridges the design gap for beginners, making it ideal for high school yearbook classes.

## Features
- **Two-Page Spread**: Visualize a 17" x 11" layout (two 8.5" x 11" pages) on a scalable canvas.
- **Bullseye Crosshairs**: Drag vertical and horizontal lines to divide the spread into four dynamic quadrants, adjusting module sizes in real-time.
- **Module Selection**: Click a quadrant to select it (highlighted with a blue border) and display a toolbar.
- **Toolbar**: Appears when a module is selected, with icons to add:
  - **Title**: Large, bold text (e.g., “Module Title”).
  - **Copy**: Body text (e.g., sample paragraph).
  - **Photo**: Placeholder image (planned: uploadable).
  - **Caption**: Small text below photos.
  - **Shape**: Rectangle placeholder (planned: customizable shapes/colors).
- **Element Tiling**: Added elements are automatically stacked vertically within the selected module.
- **Four Modules**: Each quadrant supports multiple elements, with placeholders if empty.
- **Title Element**: A prominent title placeholder on the spread (planned: editable).
- **Page Number and Label**: Fixed in the lower-left corner (e.g., “Page 1 - Senior Events”).
- **Sidebar Tools**: Placeholder buttons for adding text, uploading photos, adding shapes, editing titles, and exporting designs (planned: integration with toolbar).
- **Responsive Design**: Mobile-friendly interface with a collapsible sidebar and adaptive toolbar for classroom use.
- **Earthy Aesthetic**: Clean, modern look with greens, browns, and blues, inspired by natural tones.

*Note*: PrintVis is a prototype. Features like text editing, photo uploads, shape customization, and exporting are planned for future updates.

## Usage
1. Open PrintVis in a browser (e.g., visit the hosted version at `[your GitHub Pages URL]` or run locally; see Installation).
2. Explore the 17" x 11" spread canvas, showing two 8.5" x 11" pages side by side.
3. Drag the red crosshairs (vertical and horizontal lines) to adjust the four quadrants’ sizes.
4. Click a quadrant to select it (a blue border appears) and display the toolbar.
5. Use the toolbar icons to add elements to the selected module:
   - **T**: Add a title.
   - **C**: Add body text (copy).
   - **P**: Add a photo placeholder.
   - **Cp**: Add a caption.
   - **S**: Add a shape placeholder.
6. View added elements, which stack vertically in the module (e.g., title at top, copy below).
7. Check the spread title (“Spread Title”) and page number/label (“Page 1 - Senior Events”) in the lower-left corner.
8. Explore the sidebar tools (currently placeholders for future functionality).
9. Test on mobile devices to ensure the sidebar collapses, the toolbar adapts, and the canvas scales properly.

*Planned*: Edit text, upload photos, customize shapes, and export designs as PNGs.

## Installation (for Development)
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/PrintVis.git
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

*Note*: PrintVis uses CDN-hosted React and Tailwind CSS, requiring an internet connection for the prototype.

## Contributing
We welcome feedback and contributions from students, educators, and developers! To contribute:
1. Fork the repository on GitHub.
2. Create a new branch for your feature or fix (e.g., `git checkout -b feature/photo-upload`).
3. Commit your changes (e.g., `git commit -m "Add photo upload functionality"`).
4. Push to your fork (e.g., `git push origin feature/photo-upload`).
5. Open a pull request on the [PrintVis GitHub repository](https://github.com/yourusername/PrintVis).

Suggestions for new features (e.g., text editing, templates, undo/redo) are encouraged! Submit ideas via GitHub Issues.

## License
© 2025 Ken Kapptie. For educational use only. All rights reserved.