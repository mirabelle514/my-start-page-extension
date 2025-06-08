# Chrome Extensions

## Custom Start Page

A customizable browser start page that allows users to organize bookmarks by category and apply beautiful themes. Features include theme management, link organization, editing capabilities, and a collapsible sidebar.

### Theme Management
- **5 Built-in Themes**: Minimalist Neutral, Elegant Midnight, Soft Pastel, Modern Tech, Earthy Organic
- **Custom Color Mapping**: Map any theme color to page elements (background, cards, headers, text)
- **Visual Theme Selector**: Color swatches for easy theme preview
- **Persistent Settings**: All theme choices saved automatically

### Link Organization
- **Category-Based Organization**: Group links into custom categories
- **Inline Category Creation**: Add new categories on-the-fly
- **Grid Layout**: Responsive card-based display
- **Visual Feedback**: Hover effects and smooth transitions

### Editing Capabilities
- **Link Editing**: Modify title, URL, and category for existing links
- **Category Editing**: Rename categories (updates all associated links)
- **Delete Operations**: Remove individual links or entire categories
- **Modal Interface**: Clean editing experience with keyboard support

### User Interface
- **Collapsible Sidebar**: Toggle theme controls to maximize content space
- **Responsive Design**: Works seamlessly on mobile and desktop
- **Keyboard Navigation**: Full keyboard support for accessibility
- **Visual Indicators**: Clear buttons and hover states

## Technical Details

### File Structure
```
start.html
├── Embedded CSS (styles)
├── Embedded JavaScript (functionality)
└── No external dependencies
```

### Data Models

#### Link Object
```javascript
{
  title: "String",    // Display name
  url: "String",      // Full URL with protocol
  category: "String"  // Category name
}
```

#### Theme Object
```javascript
{
  "--primary": "#color",     // Main brand color
  "--secondary": "#color",   // Secondary elements
  "--accent": "#color",      // Accent/highlight color
  "--background": "#color",  // Page background
  "--text": "#color"         // Text color
}
```

### Storage Schema

#### localStorage Keys
- `customLinksWithCategories` - JSON array of link objects
- `customCategories` - JSON array of category names
- `selectedTheme` - Current theme name
- `--page-bg`, `--card-bg`, `--header-color`, `--text-color` - Color mappings
- `sidebarCollapsed` - Boolean for sidebar state

## Browser Compatibility
- **Required**: Modern browser with CSS Grid, Custom Properties, and localStorage
- **Tested**: Chrome 90+, Firefox 88+, Safari 14+, Edge 90+
- **Mobile**: Responsive design works on iOS Safari and Chrome Mobile

## Performance & Security
- Single HTML file loads quickly
- No external dependencies or network requests
- Efficient DOM manipulation with minimal reflows
- All URLs opened in new tabs (`target="_blank"`)
- No eval() or innerHTML with user content
- Safe localStorage wrapper handles edge cases
- Input validation for URL format

## Customization Guide

### Adding New Themes
1. Add theme object to `themes` constant
2. Include 5 color values: primary, secondary, accent, background, text
3. Theme automatically appears in selector

### Modifying Default Colors
Edit the `:root` CSS variables at the top of the style section.

### Changing Fonts
Modify the `--font-family` CSS variable or update the font-family declarations.

### Adjusting Grid Layout
Modify `grid-template-columns: repeat(auto-fit, minmax(180px, 1fr))` values to change card sizing.

## Troubleshooting

### Common Issues
- **Links Not Saving**: Check browser's localStorage quota and permissions
- **Theme Not Applying**: Verify browser CSS Custom Properties support and theme existence
- **Layout Issues**: Check browser CSS Grid support and viewport settings

## Future Enhancements
- Data import/export functionality
- Search and filter capabilities
- Drag-and-drop reordering
- Icon support for links
- Backup to cloud storage
- Keyboard shortcuts
- Dark/light mode toggle
- Analytics dashboard
