# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Sweet Slideshow is a minimalist web application that displays a slideshow of images fetched from an AWS Lambda endpoint. It features two main display modes:

1. **Regular Mode**: Shows images with the date they were taken and the current time
2. **Clock Mode**: Displays a larger clock interface with day, date, and time alongside images

## Running the Application

To run the application:

1. Open `index.html` directly in a web browser
2. Append necessary query parameters:
   - `apiKey`: Required parameter with your API key
   - `mode`: Optional, set to 'clock' for clock mode
   - `timing`: Optional, set to 'slow' for 60-second intervals (default is 15 seconds)

Example URL:
```
index.html?apiKey=YOUR_KEY&mode=clock&timing=slow
```

## Code Architecture

The application uses a simple, single-file architecture:

- `index.html`: Contains all HTML, CSS, and JavaScript
  - No build process or external dependencies required
  - Uses pure JavaScript and modern Web APIs

### Key Components

1. **Image Display**:
   - Fetches images from Lambda endpoint with viewport dimensions
   - Updates at intervals based on configuration (15s default, 60s for slow/clock mode)

2. **Clock Display**:
   - Regular mode: Shows date taken and current time
   - Clock mode: Shows day, month, date, and current time in larger font

3. **Screen Management**:
   - Fullscreen toggle on click
   - Wake Lock API to prevent screen sleep

### API Integration

The application fetches images from:
```
https://7iwwtnbtxomprzu2jb4i3osola0dyflt.lambda-url.us-east-1.on.aws
```

Parameters sent to the API:
- `viewportWidth`: Browser viewport width
- `viewportHeight`: Browser viewport height
- All other query parameters from the URL

## Development Notes

1. **Feature Management**:
   - Features are controlled via URL parameters
   - No separate configuration files or build process

2. **Display Modes**:
   - Regular mode: `mode` parameter not set
   - Clock mode: `mode=clock` (larger font, different time display)

3. **Timing Control**:
   - Default: 15-second intervals
   - Slow: 60-second intervals (set via `timing=slow` or automatically in clock mode)

## Recent Changes

Recent development has focused on:
- Improving the clock mode display
- Fixing issues with date display in non-clock mode
- Adjusting font sizes for better readability
- Adding slow shuffle option
- Error handling for missing API key

## Useful Git Commands

```bash
# View project history
git log --oneline

# Check status
git status
```