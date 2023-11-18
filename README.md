# Modern Website Starter Template

A modern website starter template emphasizing modularity, accessibility, and best practices. Utilizes BEM (Block Element Modifier) methodology for naming conventions and the 7-1 Pattern for Sass to structure stylesheets, along with Sass and CSS Grid for efficient and scalable styling. The template includes advanced responsive image techniques and a step-by-step walkthrough using feature branching in Git. Uncompiled Sass files come with helpful comments.

## Table of Contents
- [BEM](#bem-block-element-modifier)
- [7-1 Architecture](#7-1-architecture)
- [Features](#features)
- [Project Setup Instructions](#project-setup-instructions)
- [CSS Build Process](#css-build-process)
- [Contributing](#contributing)
- [License](#license)


## BEM (Block Element Modifier)
BEM is a methodology that helps create reusable and maintainable components in web development. It promotes a clear naming convention by dividing the classes into Blocks, Elements, and Modifiers as `block__element--modifier` consecutively. This ensures a structured and organized CSS codebase.


## 7-1 Architecture for Sass
The 7-1 Pattern is a popular way to organize Sass files in larger projects. It involves separating the stylesheets into seven folders (base, components, layouts, pages, themes, abstracts, and vendors) and using a single main.scss file to import all partials. The main.scss file is then used for compiling the css stylesheets. This structure encourages modularity and scalability, making it easier to manage and maintain stylesheets in complex projects.


## Features
- **Modularity:** Utilizes BEM and the 7-1 Pattern for Sass to emphasize modular design and maintainability.
- **Accessibility:** Emphasizes best practices for creating accessible web content.
- **Responsive Design:** Utilizes CSS Grid and advanced responsive image techniques such as art direction and density/resolution switching.
- **Git Workflow:** Provides a step-by-step walkthrough using feature branching in Git.
- **Sass Comments:** Includes helpful comments in uncompiled Sass files for better understanding and maintainability.


## Project Setup Instructions
Check if Node is first installed with command below. Otherwise install Node on your machine.

`node -v`

### Dependencies In package.json File
The package.json file lists package dependencies to combine css files, add css prefixes, and compresses the final style.css file. These are all consequently run by the npm-run-all package. 


### A Note On The concat:css script In package.json
The concat:css script in package.json assumes that there are additional css files in the project, and a css/icon-font.css file in particular. This is just as a reference for setting up your project. You can modify the concat:css script in package.json for any of the 3 following scenarios: 
- If you have a different css file that you want to concatenate instead, you simply change the name of the icon-font.css file to reflect your other css file. 
- If you have more css files, add them to the command after css/main.css. 
- If you do not have any additional css files, you can delete the concat script and then in the prefix:css script, change css/style.concat.css to css/main.css as that will be the file up at that stage of the build process.

### Installing The Package Dependencies
When first opening the project, install the dependencies with the command:

`npm install`

### Visual Studio Code Configuration
The project uses __Visual Studio Code__ and expects the __Live Sass Compiler__ extension by Glenn Marks and __Live Server__ extension by Ritwick Dey to be installed and configured. 

Below are the settings used in VS Code's settings.json file to configure the Live Sass Compiler for the project workflow:
    

```json
"liveSassCompile.settings.compileOnWatch": false,
"liveSassCompile.settings.watchOnLaunch": true,
"liveSassCompile.settings.useNewCompiler": true,
"liveSassCompile.settings.showOutputWindowOn": "Warning",
"liveSassCompile.settings.formats": [
  {
    "format": "expanded",
    "extensionName": ".css",
    "savePath": "~/../css",
    "savePathReplacementPairs": {
      "/sass/": "/css/"
    }
  }
],
"liveSassCompile.settings.excludeList": [
  "/**/node_modules/**",
  "/.vscode/**"
],
"liveSassCompile.settings.autoprefix": true
```

### Compiling Sass 
With these two extensions installed, there will be a "Watch Sass" and "Go Live" buttons in the footer of the VS Code app. Turn both of these on while working through your project to generate and automatically compile your Sass to css/main.css and to view your progress in a browser.


## CSS Build Process
### Stylesheet Generation

The final style.css and style.min.css files are meant to be generated when the project is ready for delivery, not repeatedly throughout the development process (the main.scss will be generated automatically by the Live Sass Compiler extension for VS Code throughout the development process). 

The final css files are generated with the command: 

`npm run build:css`


### Update The Linked Stylesheet in HTML
The stylesheet link in the HTML document(s) will need to be updated to reflect the final css file to be used.


## Contributing

Contributions are welcome! For details on how to get started, submitting bug reports, feature requests, and guidelines for pull requests, please refer to our [Contributions Guide](https://github.com/indigetal/modern-website-starter/blob/main/CONTRIBUTING.md). We appreciate your support in improving this project! 8-)


## License

This project is licensed under the [GNU GENERAL PUBLIC LICENSE Version 3](https://www.gnu.org/licenses/gpl-3.0.en.html).


