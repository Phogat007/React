# Chapter 02 - Igniting our App

## Theory Assignment

### Q: What is `npm`?
A: npm (Node Package Manager) is a tool that helps JavaScript developers manage and share reusable code packages. It allows programmers to easily find, install, and integrate these packages into their projects, saving time and effort. By using npm, developers can avoid reinventing the wheel and rely on a vast ecosystem of pre-built modules. It's like borrowing tools from a community toolbox instead of making them yourself.

---

### Q: What is a `bundler`?
A: A `bundler` is a tool in web development that combines multiple files, such as JavaScript, CSS, and images, into optimized bundles for better browser performance. It:
- Ensures proper dependency management by including files in the correct order.
- Removes redundant code to improve efficiency.
- Provides features like minification (reducing file size), transpilation (converting modern syntax to older versions), and code splitting (loading only required parts).

Examples of popular bundlers include Webpack, Parcel, and Rollup.

---

### Q: What's `Webpack`? Why do we need it?
A: Webpack is a powerful bundling tool that organizes and optimizes your project's files, including JavaScript, CSS, and assets. Key reasons to use Webpack include:
- Bundling files for faster website performance.
- Managing dependencies between files.
- Transpiling modern code for older browsers using tools like Babel.
- Splitting code into smaller parts for efficient loading.
- Offering a development server with live reload functionality.

In short, Webpack simplifies the process of preparing web projects for production.

---

### Q: How does `Webpack convert code for different browsers`?
A: Webpack doesn’t directly convert code for browser compatibility. Instead, it integrates with tools like Babel, which transpile modern JavaScript into older syntax. Webpack’s configuration uses a Babel loader to transform JavaScript files during the build process. This ensures the final bundled code works across a wide range of browsers.

---

### Q: What is `Babel`?
A: Babel is a popular open-source JavaScript compiler that converts modern JavaScript (ES6+ and beyond) into older syntax compatible with legacy browsers. It:
- Parses modern JavaScript code.
- Applies specified transformations.
- Outputs equivalent code in a more widely supported version.

This process, called transpilation, ensures developers can use the latest features without worrying about browser compatibility.

---

### Q: What is `Parcel`?
A: Parcel is a zero-configuration web application bundler that simplifies the process of building and packaging projects. Key features of Parcel include:
- Automatic asset handling without complex setup.
- A fast development server.
- Support for multiple file types and formats.
- Automatic dependency resolution.

Parcel is ideal for developers seeking an easy-to-use solution for small to medium-sized projects.

---

### Q: What is the `difference between Webpack and Parcel`?
A: While both Webpack and Parcel are bundling tools, they differ in several ways:

#### Configuration:
- **Webpack**: Highly configurable but requires manual setup.
- **Parcel**: Zero-config approach; minimal setup required.

#### Ease of Use:
- **Webpack**: More complex; better suited for advanced use cases.
- **Parcel**: Simpler and quicker to get started.

#### Features:
- **Webpack**: Offers advanced features like fine-grained control over assets, code splitting, and custom plugins.
- **Parcel**: Built-in features like a fast dev server and automatic dependency resolution.

#### Use Cases:
- **Webpack**: Ideal for large, complex projects.
- **Parcel**: Best for smaller projects and prototypes.

---

### Q: What is `.parcel-cache`?
A: The `.parcel-cache` directory is created by Parcel to store intermediate files and cached data from previous builds. It:
- Speeds up future builds by reusing processed content.
- Stores transformed assets and code.

While this cache improves performance, you can delete it if you encounter build issues. However, clearing the cache will slightly increase build time for the next run.

---

### Q: What is `npx`?
A: `npx` is a command-line tool that comes with npm, allowing you to execute Node.js packages without globally installing them. For example:

#### Running Parcel with `npx`:
1. Open the terminal and navigate to your project’s root directory.
2. Run: `npx parcel index.html` (replace `index.html` with your entry file).
3. Parcel will bundle and optimize your project, providing a local server address (e.g., `http://localhost:1234`) to view the application.

---

### Q: What is the difference between `devDependencies` and `dependencies`?
A:
- **`dependencies`**: Packages required for the application to run in production (e.g., React).
- **`devDependencies`**: Packages used only during development (e.g., testing tools like Jest or bundlers like Parcel).

This distinction helps keep production environments lightweight by excluding unnecessary development tools.

---

### Q: What is `Tree Shaking`?
A: `Tree shaking` is a technique to remove unused code from JavaScript bundles, optimizing file sizes and improving performance. During the build process:
- The bundler creates a dependency graph.
- It identifies and eliminates unused code, retaining only necessary parts.

This results in smaller and faster-loading web applications.

---

### Q: What is `Hot Module Replacement`?
A: `Hot Module Replacement` (HMR) is a feature in modern development tools that updates changes in your code instantly without reloading the entire page. It:
- Speeds up the development process.
- Retains application state during updates.
- Improves developer productivity by providing immediate feedback.

Here is an updated and slightly refined version of your content:

---

### Change Detection
When you modify your code (e.g., update a JavaScript file or tweak a CSS style), the Hot Module Replacement (HMR) system detects these changes.

### Patch and Apply
Instead of reloading the entire page or application, HMR takes the updated module (JavaScript, CSS, or other assets) and patches the changes into the running application in real time.

### Preserve State
HMR is designed to maintain the application's current state. This ensures that if you're in the middle of an interaction or have data stored in memory, those states remain intact after the code changes are applied.

### Selective Updates
HMR updates only the modified modules, reducing the need for a full page reload and speeding up the development process.

---

### Q: Does Parcel bundler have HMR?
**A:** Yes, Parcel has built-in Hot Module Replacement (HMR) functionality. As a zero-config bundler, Parcel enables HMR by default when you run its development server. 

Parcel detects your application's entry point and automatically sets up the development server with HMR enabled. Changes to React components, styles, or other assets are reflected in real time, enhancing your development workflow without requiring full page reloads.

---

### Q: List your `favorite 5 superpowers of Parcel` and describe any 3 of them.
**A:**
1. **Zero-Config Setup**  
   Parcel requires no manual configuration, automatically detecting and bundling assets. This makes it beginner-friendly and perfect for rapid prototyping.

2. **Hot Module Replacement (HMR)**  
   HMR is built into Parcel, allowing you to see instant updates as you code. This feature significantly improves iteration speed.

3. **Efficient Caching**  
   Parcel uses a sophisticated caching mechanism that speeds up rebuilds by leveraging data from previous builds.

4. **Optimized Output**  
   In production mode, Parcel optimizes assets by minifying JavaScript and CSS, generating cache-busting filenames, and applying other enhancements for performance.

5. **Code Splitting**  
   Parcel automatically splits your code into optimized bundles, reducing the initial load time and improving overall performance.

---

### Q: What is `.gitignore`? What should `we add` and `not add` into it?
**A:** `.gitignore` is a configuration file that specifies which files and directories Git should ignore. This prevents irrelevant or sensitive files from being tracked.

#### What to Add:
- **Generated Files**: Compiled code, build artifacts.
- **Dependencies**: `node_modules`, `__pycache__`.
- **Sensitive Information**: API keys, credentials.
- **Logs and Reports**: Debug outputs.
- **Temporary Files**: `.env`, `.DS_Store`.

#### What Not to Add:
- **Source Code**
- **Configuration Templates**: E.g., `config.example.json`.
- **Documentation**: README files.
- **Build Files Needed for Deployment**

---

### Q: What is the difference between `package.json` and `package-lock.json`?
**A:**  
1. **`package.json`**: Contains metadata about your project (name, version, dependencies, etc.). It's used to specify which packages your project requires.  
2. **`package-lock.json`**: A detailed snapshot of the exact versions of dependencies and their sub-dependencies installed. It ensures consistency across environments.

---

### Q: Why should I not modify `package-lock.json`?
**A:** Modifying `package-lock.json` manually can lead to:
- **Version Inconsistencies**: Introduce unexpected bugs due to mismatched dependencies.
- **Dependency Resolution Issues**: Conflicts or missing dependencies.
- **Collaboration Challenges**: Merge conflicts in team environments.

---

### Q: What is `node_modules`? Should it be pushed to Git?
**A:** `node_modules` is a directory created by Node.js to store project dependencies. It is **not** recommended to push it to Git due to its size and regenerable nature using `package.json` and `package-lock.json`.

---

### Q: What is the `dist` folder?
**A:** The `dist` (distribution) folder contains the final compiled or optimized code ready for deployment. It’s typically minified and optimized for performance.

---

### Q: What is `browserslist`?
**A:** `browserslist` specifies which browsers your project supports, guiding tools like Babel and Autoprefixer to ensure compatibility.

Example configuration:
```
last 2 versions
> 1%
not dead
```

---

### Q: Explain the `^` (caret) and `~` (tilde) symbols.
**A:**  
1. **Caret (`^`)**: Allows updates within the same major version (e.g., `^1.2.3` permits `1.3.0` but not `2.0.0`).  
2. **Tilde (`~`)**: Allows updates within the same minor version (e.g., `~1.2.3` permits `1.2.5` but not `1.3.0`).  

---

### Q: What are `script types` in HTML?
**A:** The `type` attribute in the `<script>` tag specifies the script's MIME type.

1. **JavaScript (default)**:  
   ```
   <script>
     console.log('Hello, world!');
   </script>
   ```

2. **Module**: Enables `import`/`export` syntax.  
   ```
   <script type="module">
     import { func } from './module.js';
   </script>
   ```