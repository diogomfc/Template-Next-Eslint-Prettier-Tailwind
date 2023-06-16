## Configurando ESLint + Prettier + Tailwind 

npm i -D @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-config-standard eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-n eslint-plugin-promise eslint-plugin-react eslint-plugin-react-hooks eslint-config-prettier eslint-plugin-prettier prettier prettier-plugin-tailwindcss eslint-plugin-import-helpers

- [@typescript-eslint/parser](https://www.npmjs.com/package/@typescript-eslint/parser) : é um analisador de código-fonte TypeScript para o Eslint. Ele permite que o Eslint entenda e analise arquivos TypeScript, para que você possa aplicar regras de linting ao código TypeScript em seu projeto

- [@typescript-eslint/eslint-plugin](https://www.npmjs.com/package/@typescript-eslint/eslint-plugin) : Estende a funcionalidade do Eslint para fornecer suporte de linting específico para o TypeScript.

- [eslint-config-standard](https://github.com/standard/eslint-config-standard) : Um conjunto de configurações do ESLint que segue o estilo de codificação padrão para JavaScript.

- [eslint-plugin-import](https://github.com/benmosher/eslint-plugin-import) : Um plugin para o ESLint que fornece regras de linting para importações e exportações de módulos JavaScript.

- [eslint-plugin-jsx-a11y](https://github.com/jsx-eslint/eslint-plugin-jsx-a11y) : Um plugin para o ESLint que fornece regras de linting para acessibilidade em código JSX (JavaScript XML).

- [eslint-plugin-n](https://github.com/nodesecurity/eslint-plugin-n) : Um plugin para o ESLint que fornece regras de linting específicas para o ambiente Node.js.

- [eslint-plugin-promise](https://github.com/xjamundx/eslint-plugin-promise) : Um plugin para o ESLint que fornece regras de linting para o uso de promessas (promises) em JavaScript.

- [eslint-plugin-react](https://github.com/yannickcr/eslint-plugin-react) : Um plugin para o ESLint que fornece regras de linting específicas para o desenvolvimento com a biblioteca React.

- [eslint-plugin-react-hooks](https://github.com/facebook/react/tree/main/packages/eslint-plugin-react-hooks) : Um plugin para o ESLint que fornece regras de linting para os hooks do React.

- [eslint-config-prettier](https://github.com/prettier/eslint-config-prettier) : Um conjunto de configurações do ESLint que desativa as regras de conflito com o Prettier, uma ferramenta de formatação de código.

- [eslint-plugin-prettier](https://github.com/prettier/eslint-plugin-prettier) : Um plugin para o ESLint que executa o Prettier como uma regra de linting, mantendo o código formatado corretamente.

- [prettier](https://github.com/prettier/prettier) : Uma ferramenta de formatação de código que pode ser integrada ao ESLint para manter a consistência e o estilo de formatação.

- [prettier-plugin-tailwindcss](https://github.com/hudochenkov/prettier-plugin-tailwindcss) : Um plugin do Prettier que melhora a formatação de código relacionado ao Tailwind CSS, um framework de CSS.

- [eslint-plugin-import-helpers](https://github.com/Tibfib/eslint-plugin-import-helpers) : é um plugin útil para garantir uma organização consistente das importações em seu código JavaScript, o que pode melhorar a legibilidade, a manutenção e a colaboração em projetos.

```js
   // .eslintrc.js
   module.exports = {
  env: {
    browser: true,
    es2021: true,
    jest: true,
  },
  extends: [
    'plugin:react/recommended',
    'plugin:react-hooks/recommended',
    'standard',
    'plugin:prettier/recommended',
  ],
  parser: '@typescript-eslint/parser',
  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: 'latest',
    sourceType: 'module',
  },
  plugins: [
    'react',
    'jsx-a11y',
    '@typescript-eslint',
    'eslint-plugin-import-helpers',
  ],
  rules: {
    'prettier/prettier': [
      'error',
      {
        printWidth: 80,
        tabWidth: 2,
        singleQuote: true,
        trailingComma: 'all',
        arrowParens: 'always',
        semi: false,
        endOfLine: 'auto',
      },
    ],
    'react/react-in-jsx-scope': 'off',
    'react/prop-types': 'off',
    'jsx-a11y/alt-text': [
      'warn',
      {
        elements: ['img'],
        img: ['Image'],
      },
    ],
    'jsx-a11y/aria-props': 'warn',
    'jsx-a11y/aria-proptypes': 'warn',
    'jsx-a11y/aria-unsupported-elements': 'warn',
    'jsx-a11y/role-has-required-aria-props': 'warn',
    'jsx-a11y/role-supports-aria-props': 'warn',
    'import-helpers/order-imports': [
      'warn',
      {
        // example configuration order-imports
        newlinesBetween: 'always',
        groups: [
          '/^react/',
          '/^next/',
          'module',
          '/^@components/',
          '/^@shared/',
          '/^@utils/',
          '/^@hooks/',
          '/^@services/',
          '/^@styles/',
          ['parent', 'sibling', 'index'],
        ],
        alphabetize: { order: 'asc', ignoreCase: true },
      },
    ],
  },
  settings: {
    react: {
      version: 'detect',
    },
    'import/parsers': {
      [require.resolve('@typescript-eslint/parser')]: ['.ts', '.tsx', '.d.ts'],
    },
  },
}
```
```js
   // .prettier.config.js
   module.exports = {
  plugins: [require('prettier-plugin-tailwindcss')],
}

   ```
