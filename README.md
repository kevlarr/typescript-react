# TypeScript-React Starter

A base repository for React projects with a few opinions...

- Static typing is better than dynamic
- CSS files are better than "CSS in JS"

## Features

**Strict null checking**

`null` hurts so this sets TypeScript to strict null checking, meaning types will be non-nullable by default
and will require union types to allow null, eg. `const arr: Array<number | null> = [1, 2, null, 4]`

**Production builds**

In `development` mode, webpack will bundle dependencies in with the build for simplicity
and generate consistent filenames, eg. "main.js".

In `production` mode, all external dependencies will, when possible, be served via CDN links
rather than bundling in with application code, making production bundles as lean as possible.
Additionally, assets will have hashed names for cache-busting.

**SCSS compilation**

Webpack will gather all imported .scss files and emit a single .css file, because CSS is powerful
and not as evil, outdated, or error-prone as the "JS all the things" community often claims.

Allows for importing component-level .scss files either via `@import './components/hello'` in `style.scss`
or within the component itself, eg. `import './hello.scss'` in `Hello.tsx`.
