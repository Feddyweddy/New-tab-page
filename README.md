# Simple Link Dashboard

This project is a single HTML file (`index.html`) that creates a highly customizable, visually appealing dashboard for your links. It reads link data from a `links.json` file and displays them in categorized rows.

## Features

*   **Link Organization**: Group your links into sections (e.g., "Watch", "Work", "Social").
*   **Custom Styling**: Use the in-page menu to adjust shortcut size, spacing, background image, and more.
*   **Dark/Light Mode**: Toggle between themes.
*   **Collapsible Sections**: Hide less-used shortcuts behind a chevron to keep your dashboard tidy.
*   **Drag & Drop**: Easily reorder your shortcuts (requires a local web server).
*   **Configuration**: Export and import your entire setup, including styling and links.

## `links2.json` Format

The `links2.json` file contains the data for all the shortcuts. It's a JSON object where each key is a section title, and the value is an array of link objects.

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
