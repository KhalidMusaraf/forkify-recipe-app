# Forkify Recipe App

A recipe-search web application built with **Vanilla JavaScript**,
**Parcel 2**, and **Sass**. The app uses the Forkify API to search for
recipes, display recipe details, adjust serving sizes, save bookmarks,
and upload custom recipes.

**Repository:**
[KhalidMusaraf/forkify-recipe-app](https://github.com/KhalidMusaraf/forkify-recipe-app)

## Features

- **Search recipes:** Search the Forkify API by recipe name or
  ingredient.
- **Paginated results:** Browse search results across pages.
- **Recipe details:** View a recipe’s image, publisher, cooking time,
  servings, ingredients, and link to the original cooking directions.
- **Adjust servings:** Increase or decrease the serving count and
  recalculate ingredient quantities.
- **Bookmarks:** Save favourite recipes and remove bookmarks when they
  are no longer needed.
- **Persistent bookmarks:** Bookmarks are stored in browser
  `localStorage`, so they remain available after a page refresh in the
  same browser.
- **Upload custom recipes:** Submit a recipe with its title, source URL,
  image URL, publisher, cooking time, servings, and ingredients.
- **Loading and error feedback:** Show loading indicators and messages
  during API operations.
- **Responsive interface:** A styled recipe interface built with Sass
  and reusable view classes.

## Technology Stack

- **HTML5** — page structure
- **CSS3 / Sass** — styling
- **JavaScript (ES6+)** — application logic and ES modules
- **Parcel 2** — development server and bundler
- **Forkify API** — recipe search, recipe details, and recipe uploads
- **Fetch API** — HTTP requests
- **Core-JS** and **regenerator-runtime** — compatibility support

## Prerequisites

Install:

- [Node.js](https://nodejs.org/) (npm is included)
- [Git](https://git-scm.com/) (if you want to clone the repository)

Check your installation:

``` bash
node -v
npm -v
```

## Getting Started

### 1. Clone the repository

``` bash
git clone https://github.com/KhalidMusaraf/forkify-recipe-app.git
cd forkify-recipe-app
```

Alternatively, download the repository ZIP from GitHub and extract it.

### 2. Install dependencies

From the project root, run:

``` bash
npm install
```

This installs the packages defined in `package.json` and creates
`node_modules/`. You do not need to copy `node_modules` from another
computer.

### 3. Start the development server

``` bash
npm start
```

Parcel starts a local development server. Open the URL printed in the
terminal; Parcel commonly uses:

``` text
http://localhost:1234
```

If that port is already in use, use the alternate URL printed by Parcel.

### 4. Create a production build

``` bash
npm run build
```

Parcel creates the production files in the `dist/` directory.

## Available Scripts

| Command         | Description                                              |
|-----------------|----------------------------------------------------------|
| `npm start`     | Starts the Parcel development server using `index.html`. |
| `npm run build` | Builds the app for production into `dist/`.              |

## How It Works

The app follows a model-view-controller style structure:

- **Model (`model.js`):** Holds application state, loads recipes and
  search results, updates servings, manages bookmarks, and uploads
  recipes.
- **Views (`views/`):** Render the search results, pagination, recipe
  details, bookmarks, and upload form.
- **Controller (`controller.js`):** Connects user interactions in the
  views to the model.
- **Helpers (`helpers.js`):** Provides shared AJAX handling, request
  timeouts, and error handling.
- **Configuration (`config.js`):** Stores API configuration and
  application constants.

## API Integration

The application uses the Forkify API:

``` text
https://forkify-api.jonas.io/api/v2/recipes/
```

The code uses these operations:

| Operation       | Purpose                                                           |
|-----------------|-------------------------------------------------------------------|
| Search recipes  | Requests matching recipes using a search query.                   |
| Load a recipe   | Fetches full details for a selected recipe ID.                    |
| Upload a recipe | Sends custom recipe data to the API using an HTTP `POST` request. |

The API configuration, including the API key value used by the app, is
located in `src/js/config.js`. If API requests fail because of access or
key restrictions, check the current Forkify API requirements and update
the configuration as appropriate. Do not commit credentials that are
intended to remain private.

## Notes and Limitations

- An internet connection is required to fetch recipes and upload custom
  recipes through the Forkify API.
- Bookmarks are stored in the current browser’s `localStorage`; they are
  not synced across browsers or devices.
- Custom recipe uploads depend on the API accepting the submitted recipe
  and the configured API key.
- The recipe’s cooking directions are linked from the recipe publisher’s
  website; the app does not host those instructions.
- This is a learning and portfolio project, not a commercial recipe
  service.

## Learning Outcomes

This project provides practice with:

- Modern JavaScript and ES modules
- DOM rendering and event handling
- Async/await and Fetch API requests
- Separation of concerns using model, view, and controller modules
- State management for search results, recipes, and bookmarks
- Local storage
- Form data handling and validation
- Sass and a Parcel-based development workflow
