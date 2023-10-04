# Setting up Webpack

I will guide you through setting up Firebase 9 and Webpack for your web development project. Firebase 9 introduces exciting features, and Webpack is a powerful tool to optimize your JavaScript bundles. Combining these two tools can enhance the development and performance of your web applications.

### Prerequisites

Before you begin, make sure you have the following prerequisites in place:

1. **Node.js**: Ensure that Node.js is installed on your computer. If not, you can download and install it from [nodejs.org](https://nodejs.org/).
2. **Text Editor**: Choose a text editor or integrated development environment (IDE) of your preference. We recommend using Visual Studio Code (VS Code) or any code editor you are comfortable with.

### Project Setup

Let's start by setting up the project structure:

1. **Create a Project Folder**: Create a new project folder where your Firebase project will reside. You can name it according to your preferences.
2. **Source Folder**: Inside your project folder, create a folder called "source." This folder will contain all your source code files.
3. **Entry JavaScript File**: Inside the "source" folder, create a new file named "index.js." This file will serve as the entry point for your JavaScript code.
4. **Distribution Folder**: Create a folder called "dist" in the root of your project directory. This is where your final bundled JavaScript code will be generated and stored.
5. **HTML Page**: Create an "index.html" file in the "dist" folder. This HTML file will serve as your webpage. We will link the bundled JavaScript file to this page later.

Here's a visual representation of the project structure:

```bash
your-project-folder/
├── dist/
│   └── index.html
└── source/
    └── index.js
```

### Installing Webpack

Now that we have our project structure in place, let's install Webpack and the Webpack CLI as development dependencies using npm (Node Package Manager). Open your terminal and run the following command inside your project folder:

```bash
npm init -y
npm install webpack webpack-cli -D
```

This command initializes a `package.json` file and installs Webpack and the Webpack CLI as development dependencies (indicated by the `-D` flag).

### Webpack Configuration

To configure Webpack, create a `webpack.config.js` file in the root of your project folder. This file will specify how Webpack should bundle your JavaScript code. Copy the following code into your `webpack.config.js` file:

```javascript
path = require('path');

module.exports = {
  mode: 'development', // Set to 'production' for production builds
  entry: './source/index.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'bundle.js',
  },
  watch: true,
};
```

Let's briefly explain each part of this configuration:

* **`mode`**: Set this to `'development'` for development builds. You can change it to `'production'` production builds, which will minify your code.
* **`entry`**: Specify the entry point for your JavaScript code. In this case, it's the `index.js` file inside the `source` folder.
* **`output`**: Define the output configuration. It specifies where the bundled JavaScript file (`bundle.js`) will be saved. The `path` property uses the `path` module to resolve the absolute path to the `dist` folder.
* **`watch`**: Enable watch mode so that Webpack automatically bundles your code when changes are detected in your source files.

### Running Webpack

With Webpack configured, you can now run it to bundle your JavaScript code. To do this, add a custom script to your `package.json` file. Open your `package.json` file and add the following script:

```json
"scripts": {
  "build": "webpack"
}
```

This script, named "build," runs the Webpack command when executed using `npm run build`.

### Linking Bundled JavaScript to HTML

Finally, let's link the bundled JavaScript file to your HTML page. Open the `index.html` file in the `dist` folder and add the following script tag at the bottom of the file, just before the closing `</body>` tag:

```html
<script src="bundle.js"></script>
```

Your HTML file should look something like this:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Firebase 9</title>
</head>
<body>
  <h1>Getting Started with Firebase 9</h1>
  <!-- Your content here -->
  <script src="bundle.js"></script>
</body>
</html>
```

### Testing Your Setup

You're now ready to test your setup. Open your terminal and run the following command:

```bash
npm run build
```

Webpack will bundle your code and output the result to the `dist` folder as `bundle.js`. Now, open your HTML page (`index.html`) in a web browser. Your web application should load successfully, and you can begin integrating Firebase for additional functionality.

With Firebase and Webpack in place, you have a powerful combination to develop and optimize web applications efficiently.

This document combines the setup of Firebase 9 and Webpack in a structured and corrected manner, allowing you to get started with your web development project seamlessly.

{% embed url="https://youtu.be/vK2NoOoqyRo?si=p9PHky-oDFCxJPB6" %}
