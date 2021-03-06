1. install this package on your terminal/cmd/powershell

```zsh
npm install tailwindcss@npm:@tailwindcss/postcss7-compat @tailwindcss/postcss7-compat postcss@^7 autoprefixer@^9`
```

or if you use yarn

```zsh
yarn add tailwindcss@npm:@tailwindcss/postcss7-compat @tailwindcss/postcss7-compat postcss@^7 autoprefixer@^9`
```

2. install craco

```zsh
npm install @craco/craco
```

or if you use yarn

```zsh
yarn add @craco/craco
```

3. in package.json
   from

```json
"start": "react-scripts start",
"build": "react-scripts build",
"test": "react-scripts test",
```

to

```json
"start": "craco start",
"build": "craco build",
"test": "craco test",
```

4. create `craco.config.js` and put this in the file

```js
module.exports = {
  style: {
    postcss: {
      plugins: [require("tailwindcss"), require("autoprefixer")],
    },
  },
};
```

5. create `tailwind.config.js` with `npx tailwind init` on your terminal

6. in the `tailwind.config.js` change the purge to

```js
purge: ['./src/**/*.{js,jsx,ts,tsx}', './public/index.html'],
```

7. in your index.css, clear all and put this line

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

8. create `.env` and put this line `SKIP_PREFLIGHT_CHECK=true`

You're finished
