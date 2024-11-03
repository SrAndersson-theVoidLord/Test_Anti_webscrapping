# Test-Anti_Webscrapping

 

This project demonstrates video playback with Digital Rights Management (DRM) protection using Shaka Player. It also incorporates several protective features for a webpage, including disabling right-click, preventing developer tools access, and blacking out content when attempting to capture screenshots or when the page loses visibility.

## Table of Contents:

- [**Introduction**](#introduction)
- [**Technologies Used**](#technologies-used)
- [**Features**](#features)
- [**Requirements**](#requirements)
- [**How to Use/Installation**](#how-to-useinstallation)
- [**How it works**](#how-it-works)
- [**Contributing**](#contributing)
- [**License**](#license)

## Introduction

This project is a demo implementation of a DRM-protected video player using Shaka Player. In addition to video playback, it includes several security and content protection mechanisms to prevent unauthorized access and usage of the content on the page.

## Features

- **DRM-protected video playback** using Shaka Player.
- **Disables right-click** on the page to prevent easy content copying.
- **Prevents drag actions** on specific elements to protect images and other assets.
- **Disables keyboard shortcuts** that could be used to open developer tools (e.g., F12, Ctrl+Shift+I).
- **Blackout effect** upon exiting fullscreen mode to deter screen captures.
- **Visibility detection** to apply content blackout when the page loses focus or visibility, with additional protection on Android devices.
- **Prevent external embedding** by redirecting if accessed from an iframe.

## Technologies Used

- **JavaScript**: For DOM manipulation, event handling, and Shaka Player integration.
- **Shaka Player**: Open-source JavaScript library for video playback with DRM.
- **HTML5**: Basic structure of the webpage and video element.
- **CSS**: For blackout effect styling and layout.

#### Requirements

- **Shaka Player library**: Included via `<script src="https://cdn.jsdelivr.net/npm/shaka-player@3.0.10/dist/shaka-player.compiled.js"></script>` in the HTML file.
- **Web browser with DRM support**: Some features may only work in browsers with specific DRM and visibility APIs.

## How to Use/Installation

### Windows, Linux, Mac

#### Installation

1. **Clone the repository**:

    ```bash
    git clone https://github.com/username/repositoryname.git
    cd repositoryname
    ```

2. **Set up Shaka Player**: 
   Ensure the Shaka Player library is available and linked in the HTML file as shown below:
   
   ```html
   <script src="https://cdn.jsdelivr.net/npm/shaka-player@3.0.10/dist/shaka-player.compiled.js"></script>

### Usage Instructions

1. **Open** the `index.html` file in a supported browser.
2. **Test DRM functionality** by attempting to view the protected video content. Additional protection mechanisms like right-click blocking and shortcut prevention will be active on load.


### How it works

- **DRM Setup with Shaka Player**:  
  On page load, `initShakaPlayer()` is called to configure Shaka Player and attempt to load a DRM-protected video stream. If successful, the video is loaded and ready for playback; otherwise, an error is logged.

- **Prevent Context Menu and Dragging**:
  - Right-click is disabled across the page using the `contextmenu` event prevention.
  - Specific elements, such as images, have `draggable="false"` set to prevent asset dragging.

- **Keyboard Shortcut Blocking**:  
  Common keyboard shortcuts for developer tools are blocked using the `onkeydown` event listener.

- **Fullscreen Change Detection**:  
  When the user exits fullscreen mode, a blackout effect is applied to the content, and a warning message appears. This helps deter screen capturing during playback.

- **Visibility Change Detection**:  
  Uses the `visibilitychange` event to detect if the page is hidden. If the page is hidden or minimized, a blackout effect is applied to the content.

- **Android-Specific Protection**:  
  When the page loses visibility on Android devices, an alert warns of possible screen capture attempts, and sensitive content is blurred.

- **Prevent External Embedding**:  
  If the content is accessed from an iframe on an external site, the script redirects the user back to the original URL to avoid embedding on unauthorized pages.

---

### Contributing

If you'd like to contribute to the project, feel free to fork the repository, make your changes, and submit a pull request. Any improvements or suggestions are highly appreciated.

1. Fork the project.
2. Create a new branch.
3. Make your changes and commit them.
4. Submit a pull request.

---

### License

This project is licensed under the MIT License. Feel free to use, modify, and distribute the code.

**The MIT License (MIT)**  
Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so.



