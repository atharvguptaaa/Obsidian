folder structure
![[Pasted image 20240727142104.png]]

Index.css

```css
@tailwind base;
@tailwind components;
@tailwind utilities;

@font-face{
    font-family:"Qualigo";
    src: local("Qualigo Regular - Demo"),
    url('./assets/fonts/Qaligo Regular - Demo.otf') format("opentype");

};
```

tailwind.config.js

```js
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {
      fontFamily:{
        qualigo:['Qualigo']
      }
    },
  },
  plugins: [],
}

```