---
page-title: "Aliasing paths in Vite projects w/ TypeScript - DEV Community"
url: https://dev.to/tilly/aliasing-in-vite-w-typescript-1lfo
date: "2023-08-02 22:11:02"
---

> Aliasing paths can be a really handy way of referencing key directories in your project within deeply nested files. For example, take a look at the structure of this fictitious Vite TypeScript project:  
> 
> ```
> .
> ├── index.html
> ├── package-lock.json
> ├── package.json
> ├── public
> │   └── vite.svg
> ├── src
> │   ├── App.tsx
> │   ├── assets
> │   │   ├── image.png
> │   ├── components
> │   │   ├── ComponentA
> │   │   │   └── ComponentA.tsx
> │   ├── main.tsx
> │   └── vite-env.d.ts
> ├── tsconfig.json
> ├── tsconfig.node.json
> └── vite.config.ts
> ```
> 
> Enter fullscreen mode Exit fullscreen mode
> 
> Let's say we wanted to import `image.png` from `ComponentA.tsx`. Our import would look like this:  
> 
> ```
> import image from '../../../assets/image.png';
> ```
> 
> Enter fullscreen mode Exit fullscreen mode
> 
> Not so nice. With deeply nested structures you can end up with even longer paths. It'd be a lot nicer if we could just alias the key folders and do something like this instead:  
> 
> ```
> import image from `@assets/image.png`
> ```
> 
> Enter fullscreen mode Exit fullscreen mode
> 
> Let's see how we can do that in Vite.
> 
> ## [](https://dev.to/tilly/aliasing-in-vite-w-typescript-1lfo#step-1-add-aliases-to-viteconfigts)Step 1 - Add aliases to vite.config.ts
> 
> Our first step is to register aliases with Vite (and Rollup, which Vite uses under the hood). We can do that in our `vite.config.ts`:  
> 
> ```
> import { defineConfig } from 'vite'
> import react from '@vitejs/plugin-react'
> import path from 'path';
> 
> // https://vitejs.dev/config/
> export default defineConfig({
>   resolve: {
>     alias: {
>       '@': path.resolve(__dirname, './src'),
>       '@assets': path.resolve(__dirname, './src/assets'),
>       '@components': path.resolve(__dirname, './src/components'),
>     },
>   },
>   plugins: [react()]
> })
> ```
> 
> Enter fullscreen mode Exit fullscreen mode
> 
> *Side note - make sure to `npm install -D @types/node` in order to avoid issues with importing `path` and using `__dirname`*
> 
> Now Vite knows to reference the `src` directory whenever we use `@` in our imports.
> 
> ## [](https://dev.to/tilly/aliasing-in-vite-w-typescript-1lfo#step-2-add-aliases-to-tsconfigjson)Step 2 - Add aliases to tsconfig.json
> 
> The TypeScript compiler also needs to know about our aliases so that it can compile all of our imported files. Let's update our `tsconfig.json` accordingly:  
> 
> ```
> {
>   "compilerOptions": {
>     // ... your other compiler options
>     "baseUrl": ".",
>     "paths": {
>       "@/*": ["src/*"],
>       "@components/*": ["src/components/*"],
>       "@assets/*": ["src/assets/*"]
>     },
>   },
>   "include": ["src"],
>   "references": [{ "path": "./tsconfig.node.json" }]
> }
> ```
> 
> Enter fullscreen mode Exit fullscreen mode
> 
> There's a slight syntax difference between what we added in our `vite.config.ts`, but the idea is the same. There's also a `baseUrl` property to specify what our `paths` are relative to.
> 
> ---
> 
> That's about all there is to it. Now you can use `@`, `@assets`, and `@components` in your import paths. I kept this example to three aliases for simplicity's sake, but feel free to use as many as your project calls for. Enjoy!
