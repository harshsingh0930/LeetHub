<h1 align="center">
  <img src="assets/octocode.png" alt="Harsh's LeetHub" width="400">
  <br>
  Harsh's LeetHub
  <br>
  <sub><b>Local-First</b> • Your Code • Your GitHub • Your Control</sub>
  <br><br>
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="MIT License"/>
  <img src="https://img.shields.io/badge/Firefox-Extension-orange" alt="Firefox Extension"/>
</p>

---

# About

**Harsh's LeetHub** is a **Local-First** Firefox extension that automatically uploads your accepted **LeetCode** and **GeeksforGeeks** solutions directly to **your own GitHub repository**.

Unlike cloud-based services, Harsh's LeetHub doesn't rely on any third-party backend to store or process your solutions. The extension communicates directly with GitHub using **your own OAuth application**, giving you complete control over where your code is stored.

Whether you choose a **public** repository to showcase your coding journey or a **private** repository for personal practice, your data always remains under your control.

This project is based on the open-source **[LeetHub 2.0 for Firefox](https://github.com/maitreya2954/LeetHub-2.0-Firefox)** and includes various improvements such as:

- Local-First architecture
- New branding
- Updated Firefox extension identity
- Custom GitHub OAuth configuration
- UI improvements
- Bug fixes and ongoing maintenance

---

# Features

- Local-First architecture
- Direct GitHub synchronization
- No third-party backend
- Supports both public and private GitHub repositories
- Automatically uploads accepted LeetCode solutions
- Automatically uploads accepted GeeksforGeeks solutions
- Automatically organizes problems into folders
- Automatically updates repository statistics and README
- Native Firefox support

---

# Why Local-First?

Harsh's LeetHub follows a **Local-First** approach.

- Your solutions are uploaded directly from Firefox to your GitHub repository.
- No intermediate server stores your solutions.
- You control your own GitHub OAuth application.
- You decide whether your repository is public or private.
- Your coding portfolio always remains under your ownership.

---

# How It Works

1. Install the extension.
2. Authorize with GitHub.
3. Select or create a repository.
4. Start solving problems.
5. Every accepted solution is automatically committed to your GitHub repository.

---

# GitHub OAuth Setup

This repository **does not include GitHub OAuth credentials**.

Create your own GitHub OAuth App:

1. Go to **GitHub → Settings → Developer Settings → OAuth Apps**
2. Create a new OAuth App.
3. Copy your **Client ID** and **Client Secret**.
4. Update the following files:

```
scripts/oauth2.js
scripts/authorize.js
```

---


# Local Development

Clone the repository:

```bash
git clone <your-repository-url>
cd <repository>
```

Install dependencies:

```bash
npm install
```

Run the initial setup:

```bash
npm run setup
```

Build the extension:

```bash
npm run build
```

Load it into Firefox:

1. Open `about:debugging`
2. Select **This Firefox**
3. Click **Load Temporary Add-on**
4. Select the `manifest.json` file inside the `dist` folder

Whenever you make changes, rebuild the extension:

```bash
npm run build
```

Then reload the extension from `about:debugging`.

---

# Installing Permanently in Firefox

When loaded through `about:debugging`, the extension is installed as a **temporary add-on**.

Temporary add-ons are removed whenever Firefox is restarted, updated, or crashes.

To install the extension permanently:

1. Build the extension:

```bash
npm run build
```

2. Package it as an `.xpi` file:

```bash
web-ext build --source-dir=dist
```

3. Sign the package through the Mozilla Add-on Developer Hub (Unlisted distribution is sufficient for personal use).

4. Install the signed `.xpi` file in Firefox.

Once signed, the extension remains installed permanently and no longer needs to be loaded through `about:debugging`.

> **Note:** Mozilla's signing process for unlisted extensions is typically very fast and is free to use.

---

# Available Commands

```text
npm run              Show available scripts
npm run setup        Install development dependencies
npm run build        Build the extension
npm run format       Format source files
npm run format-test  Check formatting
npm run lint         Run ESLint
npm run lint-test    Check linting
```

---

# Attribution

Harsh's LeetHub is a modified fork of the following open-source projects:

- [LeetHub](https://github.com/QasimWani/LeetHub)
- [LeetHub 2.0 for Firefox](https://github.com/maitreya2954/LeetHub-2.0-Firefox)

Many thanks to the original authors and contributors for making these projects possible.

---

# License

This project is distributed under the terms of the **MIT License**. See the [LICENSE](LICENSE) file for details.
