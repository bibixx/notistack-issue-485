# Minimal reproduction for [iamhosseindhv/notistack#485](https://github.com/iamhosseindhv/notistack/issues/485)
1. Install dependencies using `yarn` (my version is `1.22.17`)
```bash
yarn install
```

2. Run type checking
```bash
yarn run type-check
```

3. An error should appear
```
src/main.tsx:8:6 - error TS2786: 'SnackbarProvider' cannot be used as a JSX component.
  Its instance type 'SnackbarProvider' is not a valid JSX element.
    The types returned by 'render()' are incompatible between these types.
      Type 'React.ReactNode' is not assignable to type 'import("/Users/bartoszlegiec/Projects/notistack-issue-485/node_modules/@types/react-transition-group/node_modules/@types/react/index").ReactNode'.
        Type '{}' is not assignable to type 'ReactNode'.

8     <SnackbarProvider>
       ~~~~~~~~~~~~~~~~

```

## NPM
The issues doesn't seem to be happening when using `npm`
1. Head to the `npm` branch

2. Remove old `node_modules`
```bash
rm -rf node_modules
```

3. Install dependencies
```bash
npm install
```

4. Run type checking
```bash
npm run type-check
```

5. It should go through successfully, without any errors
