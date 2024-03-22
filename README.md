# Turborepo starter

This is an official starter Turborepo.

## Using this example

Run the following command:

```sh
npx create-turbo@latest
```
<img width="251" alt="turbo-1" src="https://github.com/sagarb2003/turbo-starter/assets/99736036/f43ef4f4-cce0-4d36-bce5-4647177644d2">
<img width="507" alt="turbo-2" src="https://github.com/sagarb2003/turbo-starter/assets/99736036/3a2ea371-eebf-46bd-b855-5c2c54d29dc2">

# Adding a Node.js app(little tricky)
Everything else remains the same (Create a new project, add typescript, add express…) <br/>
The only thing that’s different is that tsc doesn’t perform great with turborepo<br/>
We can use either tsup or esbuild for building our backend application<br/>

We will build using esbuild 
steps:<br/>
1) npm install esbuild in the backend folder<br/>
2) change scripts to this:=>
```sh
"scripts": {
    "build": "esbuild ./src/index.ts --bundle --platform=node --outfile=dist/index.js"
  },
```
3) npm run build<br/>
4) then backend will run fine node dist/index.js<br/>
5) Also change the tsconfig.json to this(in backend folder):=>
```sh
{
    "extends": "@repo/typescript-config/base.json",
    "compilerOptions": {
    "rootDir": "./src",
    "outDir": "./dist",
     "lib": ["ES2015"],
  },
  "exclude": ["node_modules"],
  "include": ["."]
    
}
```
Refer this for building backend with nodeJs:=> <a href="https://github.com/vercel/turbo/tree/main/examples/kitchen-sink" target="_blank" >Click</a>

# How to make a package in turborepo
For example (making a common package for zod validations)<br/>
Refer this:
<a href="https://projects.100xdevs.com/tracks/monorepo/monorepo-18" target="_blank" >Click</a>



