`import.meta.resolve(pathToDirectory)` returns a different result when running via `tsx` compared to when running the `tsc`-compiled JS via `node`.

When run via `tsx`, a trailing `/index.js` is appended to the resolved URL which is not present when running via `node`.

```console
$ node --version
v20.11.1

$ npm install

$ npm run with-tsx

> with-tsx
> tsx index.ts

file:///tsx-import-meta-resolve/node_modules/typescript/lib/index.js


$ npm run without-tsx

> without-tsx
> tsc && node index.js

file:///tsx-import-meta-resolve/node_modules/typescript/lib
```
