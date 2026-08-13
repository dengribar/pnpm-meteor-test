# pnpm-meteor-test

Run `pnpm i && pnpm run start`

There will be an error:

```
Unable to resolve some modules:
"scheduler" in /Users/den/repos/pnpm-meteor-test/node_modules/react-dom/cjs/react-dom.production.min.js (web.browser)                                       
```

which means that `react-dom` package cannot resolve its own dependency -- `scheduler` package which is located in `node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/scheduler` folder for `pnpm`'s default `nodeLinker: isolated` mode (when dependencies are symlinked from a virtual store at `node_modules/.pnpm`) ([ref](https://pnpm.io/settings/node-modules#nodelinker))