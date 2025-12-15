# Misc SD Resources V1 – Bootstrap UX Starter Dev Server

This repo contains miscellaneous resources and a **Bootstrap UX starter**.  
You can serve the HTML, CSS (Less/CSS), and JavaScript using a simple Node.js static web server with **automatic hot reload**.

This guide shows you how to:

- Install dependencies
- Run a local dev server with `npm run dev` (with auto-reload on file changes)

---

## Project Structure (Relevant Parts)

Example layout:

```text
Misc-SD-Resources-V1/
  app/
    index.html
    css/
    js/
    less/
  package.json
  README.md
```

The `app` folder contains the HTML/CSS/JS that we want to serve.

---

## Prerequisites

- [Node.js](https://nodejs.org/) (LTS recommended)
- npm (bundled with Node.js)

Verify your installation:

```bash
node -v
npm -v
```

---

## 1. Install Dependencies

From the **repository root** (the folder containing `package.json`):

```bash
cd path/to/Misc-SD-Resources-V1
npm install
```

This installs [`live-server`](https://www.npmjs.com/package/live-server) as a dev dependency.

---

## 2. Start the Dev Server

From the repo root:

```bash
npm run dev
```

This will:

- `cd` into the `app` folder
- Start `live-server` on port **8000** with hot reload enabled

You should see output like:

```text
> misc-sd-resources-v1@1.0.0 dev
> cd app && npx live-server --port=8000 --no-browser

Serving "app" at http://127.0.0.1:8000
Ready for changes
```

**Alternative:** Use `npm run dev:open` to automatically open the browser when starting the server.

---

## 3. View the Site

Open your browser and go to:

- [http://localhost:8000](http://localhost:8000)

If your main file isn’t `index.html`, open it directly, for example:

- [http://localhost:8000/home.html](http://localhost:8000/home.html)

As you edit HTML, CSS, or JS:

- Save the file
- **The browser will automatically reload** to show your changes!

> **Hot Reload Enabled:** `live-server` watches your files and automatically refreshes the browser when changes are detected. No manual refresh needed!

---

## 4. Using a Custom Port (Optional)

If port `8000` is already in use, you can use the `dev:port` script and specify another port.

From the repo root:

```bash
npm run dev:port -- 8080
```

Then open:

- [http://localhost:8080](http://localhost:8080)

---

## 5. Stopping the Server

In the terminal where `npm run dev` or `npm run dev:port` is running, press:

```text
CTRL + C
```

to stop the server.

---

## Troubleshooting

### Port Already in Use

If you see an error about port 8000 being in use:

1. Either stop whatever else is using that port, or
2. Run:

   ```bash
   npm run dev:port -- 8080
   ```

   and visit [http://localhost:8080](http://localhost:8080).

### CSS/JS Not Loading

- Ensure the dev server is running from `Bootstrap UX starter`:
  - The scripts in `package.json` already `cd "Bootstrap UX starter"` before starting `http-server`.
- Check that paths in your HTML (e.g. `<link href="css/styles.css">`) match your actual folder structure.

---

## Quick Start Summary

From a fresh clone:

```bash
cd path/to/Misc-SD-Resources-V1
npm install
npm run dev
```

Then open:

- [http://localhost:8000](http://localhost:8000)

You’ll be serving the **Bootstrap UX starter** via a simple Node.js static web server.