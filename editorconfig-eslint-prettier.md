# EditorConfig, ESLint and Prettier
Inicial configuration for JavaScript projects.

## EditorConfig
Ps: You can install EditorConfig's extension on VSCode.

Create .editorconfig file on project's root.

### .editorconfig content
```
root = true

[*]
end_of_line = lf
indent_style = space
indent_size = 2
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true
```

## ESLint
```bash
# Adds eslint as a development dependency
$ yarn add eslint -D

# Init eslint configuration
$ yarn eslint --init

# Select option "To check syntax, find problems, and enforce code style"
# Select option "JavaScript modules (import/export)"
# Select the framework you're using
# Select where code does run (Browser/Node). Ps: You can check both
# Select "Use a popular style guide"
# Select "Airbnb" or other one you prefer
# Select the config file format "JavaScript"
# Let install extensions

# When it's finished a file .eslintrc.js file will be created
```

## Prettier
```bash
$ yarn add prettier eslint-config-prettier eslint-plugin-prettier babel-eslint -D
```

## After all installed
Lets change .eslintrc.js configuration.
```javascript
// .eslintrc.js
module.exports = {
  env: {
    browser: true,
    es6: true,
  },
  extends: [
    'airbnb',
    'prettier',
    'prettier/react'
  ],
  globals: {
    Atomics: 'readonly',
    SharedArrayBuffer: 'readonly',
  },
  parser: 'babel-eslint',
  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: 2018,
    sourceType: 'module',
  },
  plugins: [
    'react',
    'prettier'
  ],
  rules: {
    'prettier/prettier': 'error',
    'react/jsx-filename-extension': [
      'warn',
      { extensions: ['.jsx', '.js'] }
    ],
    'import/prefer-default-export': 'off',
    'no-console': ['error', { allow: ['tron'] }],
    'no-param-reassign': 'off'
  },
};
```

## .prettierrc
```json
{
  "singleQuote": true,
  "trailingComma": "es5"
}
```