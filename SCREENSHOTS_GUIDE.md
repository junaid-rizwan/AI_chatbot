# Screenshots Guide

Since you don't have a Figma design file, you can use screenshots of your live application as the design reference. Here's how to create professional screenshots for your submission.

## Required Screenshots

### 1. Main Interface - Light Mode
- **What to capture**: Full chat interface with sidebar visible
- **Steps**:
  1. Open your app in browser
  2. Ensure light mode is active
  3. Have a few messages in the chat
  4. Take a full-page screenshot
  5. Save as: `screenshot-light-mode.png`

### 2. Main Interface - Dark Mode
- **What to capture**: Same view but in dark mode
- **Steps**:
  1. Toggle to dark mode
  2. Take a full-page screenshot
  3. Save as: `screenshot-dark-mode.png`

### 3. Mobile View
- **What to capture**: Responsive mobile layout
- **Steps**:
  1. Open browser DevTools (F12)
  2. Toggle device toolbar (Ctrl+Shift+M / Cmd+Shift+M)
  3. Select a mobile device (iPhone 12, etc.)
  4. Take screenshot
  5. Save as: `screenshot-mobile.png`

### 4. Model Selector Dropdown
- **What to capture**: Dropdown menu open showing models
- **Steps**:
  1. Click on model selector
  2. Wait for dropdown to open
  3. Take screenshot
  4. Save as: `screenshot-model-selector.png`

### 5. Template Manager
- **What to capture**: Template manager modal or expanded section
- **Steps**:
  1. Open template manager
  2. Show template list or create modal
  3. Take screenshot
  4. Save as: `screenshot-templates.png`

### 6. Component States (Optional but Recommended)
- **What to capture**: Hover states, focus states, etc.
- **Steps**:
  1. Hover over buttons
  2. Focus on inputs
  3. Show active states
  4. Take screenshots
  5. Save as: `screenshot-interactions.png`

## How to Take Screenshots

### Chrome/Edge (Recommended)
1. Open DevTools (F12)
2. Press `Ctrl+Shift+P` (Windows) or `Cmd+Shift+P` (Mac)
3. Type "Capture full size screenshot"
4. Select it - saves automatically

### Firefox
1. Open DevTools (F12)
2. Click the three dots menu
3. Select "Screenshot"
4. Choose "Capture full page"

### Mac (Built-in)
1. Press `Cmd+Shift+4`
2. Press `Space` to switch to window mode
3. Click on the browser window
4. Screenshot saved to Desktop

### Windows (Built-in)
1. Press `Windows+Shift+S`
2. Select area or full screen
3. Screenshot copied to clipboard
4. Paste into image editor and save

## Organizing Screenshots

Create a folder structure:
```
/public
  /screenshots
    - screenshot-light-mode.png
    - screenshot-dark-mode.png
    - screenshot-mobile.png
    - screenshot-model-selector.png
    - screenshot-templates.png
```

## Adding Screenshots to README

Add this section to your README.md Design section:

```markdown
### Screenshots

#### Light Mode
![Light Mode Interface](./public/screenshots/screenshot-light-mode.png)

#### Dark Mode
![Dark Mode Interface](./public/screenshots/screenshot-dark-mode.png)

#### Mobile View
![Mobile Interface](./public/screenshots/screenshot-mobile.png)

#### Model Selector
![Model Selector](./public/screenshots/screenshot-model-selector.png)

#### Template Manager
![Template Manager](./public/screenshots/screenshot-templates.png)
```

## Alternative: Create Simple Figma Mockup

If you want to create a quick Figma mockup (takes ~30 minutes):

1. **Sign up for Figma** (free): figma.com
2. **Create a new file**
3. **Add frames** for:
   - Desktop layout (1440x900)
   - Mobile layout (375x812)
4. **Use rectangles and text** to represent:
   - Header
   - Sidebar
   - Chat area
   - Message bubbles
5. **Add colors** from your design system
6. **Export as images** or share the Figma link

**Figma Template Structure:**
```
Frame: Desktop Layout
  ├─ Rectangle: Header (height: 64px)
  ├─ Rectangle: Sidebar (width: 320px)
  │   ├─ Rectangle: Model Selector
  │   └─ Rectangle: Parameters Panel
  └─ Rectangle: Chat Area
      ├─ Rectangle: User Message Bubble
      └─ Rectangle: AI Message Bubble
```

## Quick Figma Tips

- Use **Frames** (F) for containers
- Use **Rectangles** (R) for components
- Use **Text** (T) for labels
- Use **Auto Layout** for spacing
- Use your color palette from DESIGN_SPEC.md
- Keep it simple - it's a reference, not a detailed design

## What's Acceptable

According to the assignment, you can submit:
- ✅ Figma/XD file link
- ✅ Embedded screenshots
- ✅ Design documentation (DESIGN_SPEC.md)

Your current approach with DESIGN_SPEC.md + screenshots is perfectly acceptable!

