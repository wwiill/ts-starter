# Initialisation
```bash
mkdir src test
npm init -y
```

# Install TypeScript and types for Nodejs e.g. file, path, process
```bash
npm install typescript --save-dev
npm install @types/node --save-dev
```

# Create tsconfig.json
```bash
npx tsc --init --rootDir src --outDir build \
--esModuleInterop --resolveJsonModule --lib es6 \
--module commonjs --allowJs true --noImplicitAny true
```

# ts-node to run TypeScript code directly without transpiling to js
```bash
npm install ts-node --save-dev
```

# Testing - jest, ts-jest and types
```bash
npm install jest ts-jest @types/jest --save-dev
```

## create jest.config.js
```js
module.exports = {
    globals: {
        'ts-jest': {
            tsconfigFile: 'tsconfig.json'
        }
    },
    moduleFileExtensions: [
        'ts',
        'js'
    ],
    transform: {
        '^.+\\.(ts|tsx)$': './node_modules/ts-jest/preprocessor.js'
    },
    testMatch: [
        '**/test/**/*.test.(ts|js)'
    ],
    testEnvironment: 'node'
};
```

# es-lint
```bash
npm install --save-dev eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin
touch .eslintrc
touch .eslintignore
```

## .eslintrc
```json
{
  "root": true,
  "parser": "@typescript-eslint/parser",
  "plugins": [
    "@typescript-eslint"
  ],
  "extends": [
    "eslint:recommended",
    "plugin:@typescript-eslint/eslint-recommended",
    "plugin:@typescript-eslint/recommended"
  ]
}
```

## .eslintignore
```
node_modules
build
```

