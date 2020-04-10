## Bootstrap User Interface with Tailwindcss

### This tutorial will guide you to build your first tailwindcss project step by step

First you need to create a `package.json` file
```
npm init -y
```

Then install `tailwindcss`, `postcss-cli`, `autoprefixer`
```
npm i tailwindcss postcss-cli autoprefixer
```

Creating `tailwind.config.js` file to configure `tailwindcss`
```
npx tailwind init
```

Create a `postcss.config.js` and add this to the file
```
module.exports = {
  plugins: [
    require('tailwindcss'),
    require('autoprefixer')
  ]
}
```

Create a `css` directory and `tailwind.css` file within this folder, and add this to the file
```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Then add this script in `package.json` file
```
"scripts": {
  "build": "postcss css/tailwind.css -o public/build/tailwind.css"
```

Create a `index.html` file under `public` directory, and insert this link to `<head>`
```
<link rel="stylesheet" href="build/tailwind.css">
```

Change directory to `public` and run `live-server` to open web page and that's it, you are ready to build a dazzling app !!!
 
### Just a simple recap
- first we install a few dependencies in this case we install `autoprefixer`, `postcss-cli` and `tailwindcss`
- Next we scaffold `tailwind.config.js`, we customize our css in this file
- Then we created a `postcss.config.js`file and specity `tailwindcss` and `autoprefixer` as postcss plugins we want to use
- Then we created `tailwind.css` where we drop in three tailwind sort of markers to tell tailwind where to include generated css 
- Then we wrote a very simple build cript using `postcss-cli` to take our `tailwind.css` input file and compiled into a public directory
- Finally we created a `index.html` file and add generated css file, then we wrote a h1 tag and write a bit test codes 

### Tailwind is a postcss plugin !!!