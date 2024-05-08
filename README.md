# Basic example using typescript and @kitajs/html for jsx templating

This is a basic test of using a combination of:

- [@kitajs/html](https://github.com/kitajs/html)
- [Typescript](https://www.typescriptlang.org)
- [NodeJS](https://nodejs.org/en)

to template html strings using jsx. This mostly serves as a demonstration of a issue in combining these three to make an `esm` style application.

To demonstrate the issue first install dependencies:

```sh
npm install
```

Then try to build:

```sh
npm run build
```

Which should produce the following errors:

```
> tsc

index.tsx:2:3 - error TS2307: Cannot find module '@kitajs/html/jsx-runtime' or its corresponding type declarations.

2   <div>
    ~~~~~
3     <h1>Hello, world!</h1>
  ~~~~~~~~~~~~~~~~~~~~~~~~~~
4     <p>Welcome to the KitaJS HTML package.</p>
  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
5   </div>
  ~~~~~~~~


Found 1 error in index.tsx:2
```

This occurs because an import has been added in the transpiled code that does not specify a file extension as required by NodeJS modules.
