# Aether SaaS Bulma

Aether SaaS Bulma is a modern SaaS starter template built with [Bulma](https://bulma.io/), designed to help you quickly launch web applications with a clean, responsive UI. This project provides a solid foundation for SaaS products, admin dashboards, and web apps.

## Features

- **Bulma CSS Framework**: Fast, responsive, and easy-to-use UI components.
- **Modular Structure**: Organized codebase for scalability and maintainability.
- **Customizable**: Easily adapt styles and components to your brand.
- **Ready-to-use Pages**: Includes common SaaS pages (dashboard, login, signup, etc.).
- **Build Tools**: Integrated with gulp for development and production builds.

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v14 or higher recommended)
- [npm](https://www.npmjs.com/) or [Yarn](https://yarnpkg.com/)

- [Gulp] Installation:** Install gulp globally from your terminal

```
npm install --global gulp-cli
```

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Ephygtz/aether-saas-bulma.git
   cd aether-saas-bulma-main
   ```

2. ### Basic Usages

After downloading the template, you can simply edit the HTML and CSS files from the `theme` folder. To preview the changes you make to the code, you can open the index.html file in your web browser.

3. **Install dependencies:**
   ```bash
   npm install
   # or
   yarn install

    ```
     


### Running the Project

- **Development server:**
  ```bash
  npm start
  # or
  yarn start
  #  Run locally
  npm run dev
  ```
  The app will be available at `http://localhost:3000` (or the configured port).

- **Production build:**
  ```bash
  npm run build
  # or
  yarn build
  ```
  The optimized build will be output to the `/theme` folder.

## Project Structure

```
aether-saas-bulma-main/
├── src/                # Source code (components, pages, assets)
├── public/             # Static files
├── .gitignore
├── package.json
├── README.md
└── ...
```

## Customization

- **Bulma Variables**: Modify Bulma variables in your SCSS files to change theme colors, fonts, and more.
- **Components**: Add or update components in the `src/components` directory.
- **Pages**: Add new pages in the `src/pages` directory.

## Contributing

Contributions are welcome! Please open issues or submit pull requests for improvements and bug fixes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

- [Bulma](https://bulma.io/)
- [Node.js](https://nodejs.org/)
- [npm](https://www.npmjs.com/)

## How to Remove/Hide the Trailing `.html` in URLs

To make your URLs cleaner (e.g., `/about` instead of `/about.html`), you can use one of the following approaches depending on your hosting environment:

### 1. **Using `.htaccess` (Apache)**

Add the following to your `.htaccess` file in the root directory:

```apache
RewriteEngine On
RewriteCond %{REQUEST_FILENAME}.html -f
RewriteRule ^([^/]+)$ $1.html [L]
```

This will allow you to access `about.html` via `/about`.

### 2. **Using `netlify.toml` (Netlify)**

Add a rewrite rule to your `netlify.toml`:

```toml
[[redirects]]
  from = "/:page"
  to = "/:page.html"
  status = 200
```

### 3. **Using `nginx`**

Add a location block to your server config:

```nginx
location / {
    try_files $uri $uri.html $uri/ =404;
}
```

### 4. **Client-side Routing (Single Page Apps)**

If you use a client-side router (React, Vue, etc.), configure your router to handle clean URLs and serve the correct content.

---

Choose the method that matches your deployment environment. For static hosting, `.htaccess` or Netlify rewrites are most common.

---
Feel free to customize this README to better fit your project's specifics.
