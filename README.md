# Simple Link Dashboard

This project is a single HTML file (`index.html`) that creates a highly customizable, visually appealing dashboard for your links. It reads link data from a `links.json` file and displays them in categorized rows.

[![Watch the video](https://i.imgur.com/B7Fudy8.jpeg)](https://i.imgur.com/m34OfWx.mp4)

## Running Locally

To run this project locally, you'll need to serve it through a web server due to CORS restrictions when loading the `links.json` file.

### Quick Start (Windows)
1. Ensure Python is installed on your system
2. Double-click `run.bat` to start a local server
3. The dashboard will open automatically at `http://localhost:8000`

### Manual Setup
1. Open a terminal/command prompt in the project directory
2. Run: `python -m http.server 8000`
3. Open your browser and navigate to `http://localhost:8000`

### Alternative Servers
You can use any web server of your choice:
- Node.js: `npx serve .`
- PHP: `php -S localhost:8000`
- Live Server (VS Code extension)

## Features

*   **Link Organization**: Group your links into sections by editing the `links.json` file (e.g., "Watch", "Work", "Social").
*   **Custom Styling**: Use the in-page menu to adjust shortcut size, spacing, background image, and more.
*   **Dark/Light Mode**: Toggle between themes.
*   **Collapsible Sections**: Hide less-used shortcuts behind a chevron to keep your dashboard tidy.
*   **Global Show/Hide Toggle**: Use the "Show/Hide All" button in the burger menu to quickly toggle the visibility of all hidden shortcuts across all sections.
*   **Multiple Link Files**: Switch between different link collections by changing the filename in the code.
*   **Configuration**: Export and import your entire setup, including styling and links.

## `links.json` Format

The `links.json` file contains the data for all the shortcuts. It's a JSON object where each key is a section title, and the value is an array of link objects.

**Note**: All changes to shortcuts (adding, editing, deleting, or reorganizing) must be done by manually editing the `links.json` file. The web interface is read-only and only displays the links from the JSON file.

Each link object has the following structure:

*   `title`: The name of the shortcut displayed on the dashboard.
*   `url`: The destination URL.
*   `image`: The URL for the icon image.
*   `hidden` (optional): If set to `true`, the shortcut will be placed in the collapsible section of its category.

### Example

```json
{
  "Watch": [
    {
      "title": "YouTube",
      "url": "https://www.youtube.com/",
      "image": "https://www.google.com/s2/favicons?domain=youtube.com&sz=64"
    },
    {
      "title": "Twitch",
      "url": "https://www.twitch.tv/",
      "image": "https://www.google.com/s2/favicons?domain=twitch.tv&sz=64",
      "hidden": true
    }
  ],
  "Social": [
    {
      "title": "Twitter",
      "url": "https://twitter.com/",
      "image": "https://www.google.com/s2/favicons?domain=twitter.com&sz=64"
    }
  ]
}
```

In this example:
*   The "Watch" section has two links. "YouTube" will be visible by default, and "Twitch" will be hidden in the collapsible area.
*   The "Social" section has one link, "Twitter", which will be visible.

## Using Different Link Files

The dashboard can load different link files, making it easy to have separate collections (e.g., work links, personal links, gaming links). To switch between files:

1. Open `index.html` in a text editor
2. Find the `LINKS_FILENAME` configuration variable at the very top of the file (around line 8-10)
3. Change the value from `'links.json'` to your desired filename (e.g., `'links-work.json'`, `'links-gaming.json'`)
4. Create the corresponding JSON file with your links

This allows you to maintain multiple link collections while keeping private links separate from publicly shared ones.
