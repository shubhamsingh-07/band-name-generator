# Band Name Generator

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A small server-rendered web application built with **Node.js, Express, and EJS**. Click a button to generate a band name by combining a word from an adjective list with a word from a noun list.

## Features

- Generates a band name in response to a form submission.
- Renders the page and generated name with EJS templates.
- Uses reusable EJS header and footer partials.
- Serves the stylesheet from the Express static-files directory.
- Includes large adjective and noun word lists directly in the server code.
- Displays a welcome message before the first name is generated.

## Tech Stack

- **Node.js** — JavaScript runtime.
- **Express 4** — handles HTTP routes and serves static files.
- **EJS** — renders the HTML on the server.
- **body-parser** — parses URL-encoded form submissions.
- **HTML and CSS** — provide the page structure and styling.

## Getting Started

### Prerequisites

- Node.js installed
- npm (included with Node.js)

### 1. Clone the repository

```bash
git clone https://github.com/shubhamsingh-07/band-name-generator.git
cd band-name-generator
```

### 2. Install dependencies

```bash
npm install
```

### 3. Run the application

```bash
node index.js
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## How It Works

1. The `GET /` route renders the initial page.
2. The page displays a form with a **Generate Name** button.
3. Submitting the form sends a `POST /submit` request.
4. The route chooses a random index based on the adjective list and uses that index to select an adjective and a noun.
5. Express renders the same EJS page with the selected words, and the name appears on the page.

The template uses shared files in `views/partials/`, while the stylesheet is served from `public/styles/main.css`.

## Application Routes

| Method | Route | Purpose |
| --- | --- | --- |
| `GET` | `/` | Renders the starting page or a generated name. |
| `POST` | `/submit` | Chooses words and renders the generated name. |

## Project Structure

```text
band-name-generator/
├── index.js                 # Express server and word lists
├── package.json             # Project metadata and dependencies
├── package-lock.json        # Locked dependency tree
├── public/
│   └── styles/
│       └── main.css         # Application stylesheet
└── views/
    ├── index.ejs            # Main page and form
    └── partials/
        ├── header.ejs       # HTML head and layout start
        └── footer.ejs       # Footer and current year
```

## Current Scope and Improvements

This is a learning project focused on handling a form submission and rendering dynamic server-side content. It does not use a database, user accounts, or an external API.

Potential improvements:

- Choose adjective and noun indexes independently. The arrays currently have different lengths, but the same index is used for both selections.
- Move the word lists into separate data files to keep the route handler easier to read.
- Add automated tests for the name-generation logic and Express routes.
- Add a configurable port and clearer error handling.
- Add input options so users can influence the generated name.

## License

**MIT License** — see the [`LICENSE`](LICENSE) file for the full terms.

The repository contains large adjective and noun lists embedded in `index.js`; their source is not attributed in the project files. Confirm their provenance and any applicable terms before redistributing those lists. Third-party npm packages remain under their respective licenses.

## Author

**Shubham Singh** · [GitHub Profile](https://github.com/shubhamsingh-07)
