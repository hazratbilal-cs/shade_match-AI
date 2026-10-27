# AI Clothing Color Changer

An AI-powered web application that allows users to visualize different clothing colors in an uploaded photograph. Built with HTML, CSS, JavaScript, Tailwind CSS, and Google's Gemini image-generation API, the application aims to recolor clothing while preserving the person's appearance, clothing texture, lighting, and background.

## Overview

The **AI Clothing Color Changer** provides a simple interface for experimenting with clothing colors without manually editing an image. Users can upload a photograph, select a custom color or choose from a predefined palette, and generate an AI-edited result.

The application includes original and generated image previews, loading indicators, error handling, and an option to download the resulting image.

## Features

- **Image Upload:** Upload photographs in supported image formats through the browser's file picker.
- **Custom Color Selection:** Choose a clothing color using an interactive color picker.
- **20-Color Palette:** Select from 20 predefined clothing colors, including navy blue, black, white, charcoal gray, olive green, burgundy, beige, and crimson red.
- **AI-Powered Recoloring:** Send the uploaded image and a color-specific editing prompt to the Gemini image model.
- **Appearance Preservation:** Instruct the AI to preserve the person's face, hair, skin tone, pose, facial expression, clothing texture, folds, lighting, shadows, and background while changing the clothing color.
- **Before-and-After Preview:** Display the original photograph alongside the recolored result.
- **Image Download:** Download the generated image as a PNG file.
- **Loading Indicator:** Display a loading animation while the image is being processed.
- **Error Handling:** Show informative error messages when image generation or API requests fail.
- **Retry Mechanism:** Retry failed HTTP requests with exponential backoff.
- **Responsive Interface:** Use Tailwind CSS to create a layout that adapts to desktop and mobile screens.

## Technologies Used

- **HTML5** — Application structure and file input.
- **CSS3** — Custom styling, animations, and loading spinner.
- **JavaScript (ES Modules)** — Application logic, event handling, file processing, and API integration.
- **Tailwind CSS** — Responsive layout and interface styling.
- **Google Gemini API** — AI-based image editing and clothing recoloring.
- **FileReader API** — Read uploaded images and convert them into Base64 data.
- **Fetch API** — Send HTTP requests to the image-generation endpoint.

## How It Works

1. **Upload a photograph:** The user selects an image from their device.
2. **Preview the original:** JavaScript reads the image and displays it in the original-image panel.
3. **Choose a color:** The user selects a custom HEX color or picks one from the predefined palette.
4. **Construct the editing request:** The application combines the selected color with an instruction to preserve the rest of the photograph.
5. **Request AI image editing:** The image and prompt are submitted to the Gemini API.
6. **Process the response:** The application extracts the generated image from the API response and displays it in the result panel.
7. **Download the result:** The user can save the generated image locally.

## Project Structure

```text
ai-clothing-color-changer/
├── index.html       # HTML, CSS, interface, and JavaScript logic
└── README.md        # Project documentation
```

The current implementation places the interface, styling, and JavaScript in a single HTML file.

## Getting Started

### Prerequisites

- A modern web browser.
- Internet access to load Tailwind CSS and communicate with the Gemini API.
- A Google Gemini API key with access to a compatible image-generation model.

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/YOUR_USERNAME/ai-clothing-color-changer.git
   ```

2. Navigate to the project directory:

   ```bash
   cd ai-clothing-color-changer
   ```

3. Open `index.html` in a browser or run a local development server, such as the VS Code Live Server extension.

4. Configure the Gemini API integration before attempting AI image generation.

### API Configuration

The current frontend implementation contains an empty API key placeholder:

```javascript
const apiKey = "";
```

The application will not successfully generate recolored images until the API request is configured with a valid key and a compatible model.

**Security note:** Do not commit API keys to GitHub or expose private keys in client-side JavaScript. For a safer implementation, send image-generation requests through a backend server that stores the API key in an environment variable. Restrict API usage and monitor costs.

The configured model name and request/response format must also be compatible with the Gemini API available to your account.

## Usage

1. Open the application in your browser.
2. Upload a photograph containing visible clothing.
3. Choose a color using the custom color picker or the suggested palette.
4. Click **Apply Color Change** when using the custom color picker.
5. Wait for the AI-generated result to appear.
6. Compare the original and recolored images.
7. Click **Download Result** to save the output.

Selecting a predefined palette color automatically starts generation when an image has already been uploaded.

## Limitations

- Results depend on the image model's ability to identify and edit the intended clothing.
- The generated image may contain unintended changes to the person's appearance or background.
- Clothing boundaries, patterns, textures, and complex lighting may not always be preserved perfectly.
- Image generation requires a working API connection, a compatible model, and sufficient API quota.
- Processing time and output quality depend on the API and the input image.
- The current implementation sends uploaded photographs to an external AI service for processing. Users should avoid uploading sensitive images unless they understand and accept the service's data-handling terms.
- The current application does not include a dedicated backend or secure server-side API-key management.

## Future Improvements

- Add secure backend integration for API-key protection.
- Add file-size and image-dimension validation.
- Allow users to select a specific clothing region instead of relying entirely on AI interpretation.
- Add adjustable color intensity and more advanced color controls.
- Improve accessibility and keyboard navigation.
- Add generation history and side-by-side comparison controls.
- Add automated tests and deployment instructions.

## Author
Hazrat Bilal 

