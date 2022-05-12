mkdir src test

npm init -y
npm install typescript --save-dev

# Nodejs types for TypeScript e.g. file, path, process
npm install @types/node --save-dev

# create tsconfig.json
npx tsc --init --rootDir src --outDir build \
--esModuleInterop --resolveJsonModule --lib es6 \
--module commonjs --allowJs true --noImplicitAny true

# ts-node runs TypeScript code directly without transpiling to js
npm install ts-node --save-dev

# Testing - jest, ts-jest and types
npm install jest ts-jest @types/jest --save-dev

## create jest.config.js
```
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

