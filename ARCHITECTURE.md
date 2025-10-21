# Fort1nd macOS App Architecture

## Overview
This is an Electron-based macOS application that embeds and displays the Fort1nd website (www.fort1nd.com) in a native macOS window.

## File Structure

```
fort.mac-v2/
├── main.js          # Electron main process
├── preload.js       # Preload script for secure context
├── index.html       # UI that embeds the website
├── package.json     # Project configuration
├── .gitignore       # Git ignore rules
└── README.md        # User documentation
```

## Components

### main.js (Main Process)
- Creates and manages the application window
- Configures window preferences and security settings
- Handles app lifecycle events (ready, activate, quit)
- Sets up webview tag support for embedding external content

### preload.js (Preload Script)
- Runs before the renderer process loads
- Provides secure API bridge between main and renderer processes
- Currently exposes minimal platform information

### index.html (Renderer Process)
- Contains the user interface
- Embeds www.fort1nd.com using a webview tag
- Includes loading indicator
- Handles loading states and errors
- Implements Content Security Policy for safety

## Security Features

1. **Context Isolation**: Enabled to prevent access to Node.js APIs from web content
2. **Node Integration**: Disabled to prevent security vulnerabilities
3. **Content Security Policy**: Restricts what resources can be loaded
4. **Webview Tag**: Used instead of iframe for better control and security

## Build Process

The application uses electron-builder to create distributable packages:

- **DMG**: macOS disk image for easy installation
- **ZIP**: Compressed archive for direct distribution

### Build Targets
- ARM64 (Apple Silicon): Modern Macs with M1/M2 chips
- x64 (Intel): Older Intel-based Macs
- Universal: Automatic detection of current architecture

## Development Workflow

1. **Development**: Run `npm start` to launch the app in development mode
2. **Testing**: Test the app by navigating to the embedded website
3. **Building**: Run `npm run build` to create distributable packages
4. **Distribution**: Share the generated DMG or ZIP file

## Technical Decisions

### Why Electron?
- Cross-platform compatibility (extendable to Windows/Linux)
- Native-like performance and feel
- Easy web content embedding
- Active ecosystem and support

### Why Webview Tag?
- Better isolation than iframe
- More control over embedded content
- Can handle navigation and new windows
- Native-like behavior

### Why Not BrowserView?
- Webview is simpler for basic embedding
- Better HTML/CSS integration
- Easier loading state management

## Future Enhancements

Potential improvements for future versions:

1. Add custom application icon
2. Implement menu bar with useful actions
3. Add keyboard shortcuts
4. Implement offline detection
5. Add preferences/settings panel
6. Support for multiple windows/tabs
7. Custom user agent configuration
8. Auto-update functionality
