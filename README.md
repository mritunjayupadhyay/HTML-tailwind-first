Steps to create a fresh Tailwind starter for HTML.

1. mkdir 'Your project name'. cd 'Your project name'.
2. npm init -y.
3. npm install tailwindcss
4. create a css file.(style.css). And add folowing to it.
@tailwind base;
@tailwind components;
@tailwind utilities;
5. npm install postcss-cli autoprefixer
6. create postcss.config.js and add following
module.exports = {
  plugins: [require('tailwindcss'), require('autoprefixer')],
};
7. Create a folder src and index.html file in it.
Add build command in package.json
"build": "postcss styles.css -o src/styles.css"
8. Run npx tailwindcss init to create tailwind.config. and add the basic configuration
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./src/*.html"],
  theme: {
    extend: {},
  },
  plugins: [],
}


9. Not required but we can add live-server. run this command in terminal npm install -g live-server
10. To use live-server add this one in package.json "dev": "npm run build && live-server src --port=8080" 
11. Add concurrently and npm-watch for better development experience.