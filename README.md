# Bookmarks Browser Extension

A Chrome extension for advanced bookmark management with heterarchical organization.

## Features

- **Heterarchical Bookmark Organization**: Bookmarks can belong to multiple groups, unlike Chrome's default tree structure.
- **Semantic Search**: Find bookmarks based on meaning, not just keywords.
- **Smart Grouping**: AI-powered suggestions for organizing your bookmarks.
- **Visual Layout**: Canvas-based responsive grid for better visualization.
- **Privacy Controls**: Hide private bookmarks until explicitly requested.
- **Sublinks**: Add frequently visited pages under main bookmarks.

## Installation

### Development Mode

1. Clone this repository:
   ```
   git clone https://github.com/nicsaiart1/bookmarks-browser.git
   ```

2. Open Chrome and navigate to `chrome://extensions`

3. Enable "Developer mode" (toggle in the top-right corner)

4. Click "Load unpacked" and select the extension directory

5. The extension should now be installed and will override your new tab page

### Configuration

1. Click the extension icon in Chrome's toolbar and select "Settings"
2. Enter your Anthropic API key to enable semantic features
3. Customize appearance and behavior options

## Architecture

The extension is built on a layered architecture:

### Data Layer
- Abstract Bookmark Model: Sits on top of Chrome's bookmark API
- Storage Manager: Chrome Storage API for persistence

### UI Components
- New Tab Override: Custom bookmark visualization
- Bookmark Card Component: Displays bookmark information
- Bookmark Group Component: Container for related bookmarks
- Search Interface: Real-time search with semantic capabilities
- Side Panel: Recent/frequent sites and recommendations

### Controller Layer
- Edit Mode Controller: Manages state changes and editing operations
- Search Controller: Processes and orchestrates search mechanisms
- Group Manager: Handles creation and modification of groups

### Service Layer
- Semantic Processing Service: Interfaces with Anthropic API
- Usage Analytics Service: Tracks bookmark usage
- Settings Service: Manages user preferences

## Using Semantic Features

This extension uses Anthropic's Claude API to provide semantic search and smart grouping suggestions. To use these features:

1. Get an API key from [Anthropic Console](https://console.anthropic.com/)
2. Enter the API key in the extension settings
3. Test the connection to verify it works
4. Enable semantic features in the settings

## Development

### Project Structure
```
bookmarks-browser/
├── manifest.json                 # Extension manifest
├── background/                   # Background scripts
├── models/                       # Data models
├── services/                     # Service modules
├── components/                   # UI components
├── utils/                        # Utility functions
├── newtab/                       # New tab page
└── settings/                     # Settings page
```

### Build and Test
The extension doesn't require a build step. Changes can be tested by reloading the extension from the Chrome extensions page.

## License

MIT

## Acknowledgements

- Anthropic Claude API for semantic processing
- Chrome Extensions API