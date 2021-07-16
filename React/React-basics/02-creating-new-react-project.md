# How to create a new React project

The fastest way to create a React project is to use the [Create React App tool](https://github.com/facebook/create-react-app).

This tool gives:

1. Preconfigured folders w/ React code files
2. Config files that let you build the app for production use (bundling, polyfilling etc.)
3. Gives a dev environment w/ a web server that allows you to preview the app locally.

## Node.js

In order for this to work you need Node.js installed on your machine.

Node.js is commonly used to run JS apps outside of the browser, and therefore isn't directly needed to run React apps. However, it is needed in order to run the Create React App tool.

Ensure Node.js and npm are installed. Arch:

`sudo pacman -S nodejs npm`

## Install

`npx create-react-app folder-name`
