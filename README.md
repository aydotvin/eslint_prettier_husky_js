# ESLint, Prettier, Husky - JS Setup

## Steps:

### Basic packages:

-   Install basic eslint packages. `npm i -D eslint@latest eslint-plugin-react@latest`.
-   Install prettier packages. `npm i -D prettier eslint-config-prettier eslint-plugin-prettier`.
-   Create `.eslintrc.json` file in root folder and add the eslint config.
-   Create `.prettierrc` file in root folder and add the prettier config.

### Scripts:
```
"lint": "eslint \"src/**/*.{js,jsx}\"",
"lint:fix": "eslint --fix \"src/**/*.{js,jsx}\"",
```
`"lint": "eslint .",` to lint the entire project

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

### Husky setup:
-	`npm i -D husky-init`
-	`npx husky-init && npm install` - this will setup the husky scripts in its folder.
-	`npx husky add/set .husky/pre-commit "npm run lint"`
	-   `add` will add to existing list of commands to be run before the commit.
	-   `set` will override the existing list and only uses the newly passed command.
	-   Commands can be directly added in the "pre-commit" file in the .husky folder.
	-	The git hooks such as `pre-commit` can be found in .git/hooks/ folder of the git project.

### References
-	[ESLint rules](https://eslint.org/docs/latest/rules/)
-	[JSX ESLint rules](https://github.com/jsx-eslint/eslint-plugin-react/tree/master/docs/rules)
-	[Youtube tutorial](https://www.youtube.com/watch?v=ZXW6Jn6or1w)