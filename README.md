# ESLint, Prettier, Husky - JS Setup

## Steps:

### ESLint setup:

-   Install basic eslint packages. `npm i -D eslint@latest eslint-plugin-react@latest`.
-   Install prettier packages. `npm i -D prettier eslint-config-prettier eslint-plugin-prettier`.
-   Create `.eslintrc.json` file in root folder and add the eslint config.
-   Create `.prettierrc` file in root folder and add the prettier config.

### Config files:

-   `.eslintrc.json` config file data:

```
{
	"env": {
		"browser": true,
		"es2021": true,
		"node": true,
		"jest": true
	},
	"extends": ["eslint:recommended", "plugin:react/recommended", "plugin:prettier/recommended"],
	"parserOptions": {
		"ecmaFeatures": {
			"jsx": true
		},
		"ecmaVersion": "latest",
		"sourceType": "module"
	},
	"plugins": ["react", "prettier"],
	"settings": {
		"react": {
			"version": "detect"
		}
	},
	"rules": {
		"linebreak-style": 0,
		"quotes": ["error", "double"],
		"indent": ["error", "tab"],
		"semi": ["error", "always"],
		"react/react-in-jsx-scope": 0,
		"no-tabs": ["error", { "allowIndentationTabs": true }],
		"arrow-body-style": ["error", "as-needed"],
		"react/function-component-definition": [
			"error",
			{
				"namedComponents": "arrow-function",
				"unnamedComponents": "arrow-function"
			}
		],
		"react/jsx-indent": ["error", "tab"]
	}
}
```

-   `.prettierrc` config file data:

```
{
	"semi": true,
	"trailingComma": "all",
	"singleQuote": false,
	"printWidth": 180,
	"tabWidth": 4,
	"useTabs": true,
	"endOfLine": "auto"
}
```
