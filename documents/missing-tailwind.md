Issue: Missing tailwind in dependencies


### Step to resolve

1. ✅ Install required dependencies:
   - tailwindcss
   - postcss
   - autoprefixer

2. ✅ Create necessary configuration files:
   - tailwind.config.js - for Tailwind configuration
   - postcss.config.js - for PostCSS configuration

3. ✅ Add Tailwind directives to your CSS
   - Added `@tailwind base;`, `@tailwind components;`, and `@tailwind utilities;` to the top of styles/globals.css

### Verification
- Tailwind CSS v4.0.9 is installed
- Configuration files are created
- CSS directives are added

Now you should be able to run the `shadcn add` command successfully.

### Encounter problem
1. ✅ Issue with `npx tailwindcss init -p` command:
```
giang@MacBook-Pro-4 next-netlify-starter-demopage % npx tailwindcss init -p
npm ERR! could not determine executable to run

npm ERR! A complete log of this run can be found in:
npm ERR!     /Users/giang/.npm/_logs/2025-03-03T
```
Solution: Created configuration files manually.

2. ✅ Build issue with PostCSS configuration:
```
Error: It looks like you're trying to use `tailwindcss` directly as a PostCSS plugin. The PostCSS plugin has moved to a separate package, so to continue using Tailwind CSS with PostCSS you'll need to install `@tailwindcss/postcss` and update your PostCSS configuration.
```
Solution: Updated postcss.config.js to use `@tailwindcss/postcss` instead of `tailwindcss` directly:
```js
module.exports = {
  plugins: {
    '@tailwindcss/postcss': {},
    autoprefixer: {},
  },
}
```

