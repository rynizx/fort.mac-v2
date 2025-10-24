# fort.mac-v2
Fort1nd macOS Electron app - completely rewritten

## Description
This is an Electron-based macOS application that embeds for i promise it's not gonna be a Electron app forever ok?

## Prerequisites
- Node.js 16 or higher
- npm (comes with Node.js)

## Installation
```bash
npm install
```

## Running the App
```bash
npm start
```

## Building for macOS
Build for current architecture:
```bash
npm run build
```

Build for Apple Silicon (ARM64):
```bash
npm run build:arm64
```

Build for Intel (x64):
```bash
npm run build:x64
```

The built application will be available in the `dist` folder.

## Features
- Native macOS application using Electron
- Native window controls
- macOS-optimized UI
- Loading indicator
- Error handling for network issues
