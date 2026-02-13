1️⃣ Create project & init npm
npm init -y

2️⃣ Install Tailwind CSS
npm install -D tailwindcss @tailwindcss/cli

3️⃣ Create Tailwind config
npx tailwindcss init


This creates:

tailwind.config.js

4️⃣ Configure tailwind.config.js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./**/*.html"],
  theme: {
    extend: {},
  },
  plugins: [],
}

5️⃣ Create CSS files
Folder structure:
project/
│
├── index.html
├── tailwind.config.js
├── package.json
│
└── src/
    ├── input.css
    └── output.css

6️⃣ Add Tailwind to src/input.css (v4)
@import "tailwindcss";

7️⃣ Build Tailwind
npx tailwindcss -i ./src/input.css -o ./src/output.css --watch

8️⃣ Link CSS in HTML
index.html
<link rel="stylesheet" href="src/output.css">

9️⃣ Use Tailwind classes 🎨
<div class="bg-red-500 text-white p-4">
  Hello Tailwind!
</div>

✅ Quick Debug Checklist

If Tailwind not working, check:

✔ Tailwind installed (node_modules exists)
✔ content path correct
✔ input.css uses @import "tailwindcss"; (v4)
✔ CLI running in watch mode
✔ Hard refresh browser (Ctrl + Shift + R)

⚠️ Tailwind v3 (OLD way – only if needed)

If using Tailwind v3, use this in input.css:

@tailwind base;
@tailwind components;
@tailwind utilities;



****📝 Tailwind CSS Build Script — Notes
1️⃣ Script in package.json
"scripts": {
  "build": "tailwindcss -i src/input.css -o src/output.css --watch"
}

2️⃣ How to run this script (IMPORTANT)
✅ Correct command in terminal:
npm run build

Stop with:

Ctrl + C****