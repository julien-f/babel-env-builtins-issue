`@babel/preset-env` issue with `useBuiltIns: 'usage'` and
destructuring in `for of` loop.

Error:

```
$ babel index.js
TypeError: Cannot read property 'name' of null
    at PluginPass.VariableDeclarator (babel-presetenv-builtins-issue/node_modules/@babel/preset-env/lib/use-built-ins-plugin.js:172:47)
    at newFn (babel-presetenv-builtins-issue/node_modules/@babel/traverse/lib/visitors.js:225:21)
    at NodePath._call (babel-presetenv-builtins-issue/node_modules/@babel/traverse/lib/path/context.js:64:19)
    at NodePath.call (babel-presetenv-builtins-issue/node_modules/@babel/traverse/lib/path/context.js:38:17)
    at NodePath.visit (babel-presetenv-builtins-issue/node_modules/@babel/traverse/lib/path/context.js:95:12)
    at TraversalContext.visitQueue (babel-presetenv-builtins-issue/node_modules/@babel/traverse/lib/context.js:140:18)
    at TraversalContext.visitMultiple (babel-presetenv-builtins-issue/node_modules/@babel/traverse/lib/context.js:94:17)
    at TraversalContext.visit (babel-presetenv-builtins-issue/node_modules/@babel/traverse/lib/context.js:179:19)
    at Function.traverse.node (babel-presetenv-builtins-issue/node_modules/@babel/traverse/lib/index.js:91:17)
    at NodePath.visit (babel-presetenv-builtins-issue/node_modules/@babel/traverse/lib/path/context.js:102:18)
```

Steps to reproduce:

```
git clone https://github.com/julien-f/babel-env-builtins-issue.git
cd babel-env-builtins-issue
yarn
yarn build
```
