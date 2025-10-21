# Quick Start Guide

## Getting Started in 3 Steps

### 1. Install Dependencies
```bash
npm install
```

### 2. Run the Application
```bash
npm start
```

### 3. Build for Distribution (Optional)
```bash
npm run build
```

## What Happens When You Run It?

When you run `npm start`, the application will:
1. Open a native macOS window
2. Display a loading indicator
3. Load and display www.fort1nd.com
4. Hide the loading indicator once the site loads

## Building the App

After running `npm run build`, you'll find:
- `dist/Fort1nd-1.0.0.dmg` - Disk image for installation
- `dist/Fort1nd-1.0.0-mac.zip` - ZIP archive for distribution

## Troubleshooting

### The app won't start
- Make sure you ran `npm install` first
- Check that Node.js version is 16 or higher: `node --version`

### Website won't load
- Check your internet connection
- Verify www.fort1nd.com is accessible in a web browser

### Build fails
- Ensure all dependencies are installed: `npm install`
- Try cleaning and reinstalling: `rm -rf node_modules && npm install`

## System Requirements

- macOS 10.13 (High Sierra) or later
- Node.js 16.x or later
- npm 7.x or later

## Next Steps

- Read [ARCHITECTURE.md](ARCHITECTURE.md) to understand how the app works
- Customize the window size in `main.js` (width/height properties)
- Modify styling in `index.html` to match your preferences
