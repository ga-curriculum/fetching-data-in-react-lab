# ![Fetching Data in React Lab - Setup](./assets/hero.png)

## Setup

Open your Terminal application and navigate to your `~/code/ga/labs` directory:

```bash
cd ~/code/ga/labs
```

Create a new Vite project for your React app:

```bash
npm create vite@latest
```

You'll be prompted to choose a project name. Let's name it `fetching-data-in-react-lab`. 

- Select a framework. Use the arrow keys to choose the `React` option and hit `Enter`.

- Select a variant. Again, use the arrow keys to choose `JavaScript` and hit `Enter`.

Navigate to your new project directory and install the necessary dependencies:

```bash
cd fetching-data-in-react-lab
npm i
```

Open the project's folder in your code editor:

```bash
code .
```

### Configuring ESLint

Before we begin, we need to adjust the ESLint configuration. Add the following rules to the `.eslintrc.cjs` file:

```js
rules: {
  'react-refresh/only-export-components': [
    'warn',
    { allowConstantExport: true },
  ],
  'react/prop-types': 'off', // add this line
  'react/no-unescaped-entities': 'off' // add this line
},
```

The first addition prevents warnings if you're not declaring types for your props (which we're not), and the second prevents warnings if you're using contractions within JSX.

### Clear `App.jsx`

Open the `App.jsx` file in the `src` directory and replace the contents of it with the following:

```jsx
// src/App.jsx

const App = () => {

  return (
    <h1>Hello world!</h1>
  );
}

export default App
```

### GitHub setup

To add this project to GitHub, initialize a Git repository:

```bash
git init
```

Make a new repository on [GitHub](https://github.com/) named `fetching-data-in-react-lab`. 

Link your local project to your remote GitHub repo:

```bash
git remote add origin https://github.com/<github-username>/fetching-data-in-react-lab.git
git push origin main
```

> 🚨 Do not copy the above command. It will not work. Your GitHub username will replace `<github-username>` (including the `<` and `>`) in the URL above.








Now let's get the file and folder structure set up for our project.

- Create a new folder called `components` in the `src` directory.
- Create a new folder called `services` in the `src` directory.
- Inside of `services` create a new file called `petService.js`.
- Inside of `petService.js` create add the base URL for our API.

```js
const BASE_URL = `${import.meta.env.VITE_BACK_END_SERVER_URL}/pets`
```

- Create a `.env` file in the root of the project and add the following:

```bash
VITE_BACK_END_SERVER_URL='http://localhost:3000'
```

We are going to keep any components we create inside the `components` directory. This will help us keep our project organized and easy to navigate. We are also going to create a file called `petService.js` that will hold the base URL for our API. This will help us keep our code DRY and easy to maintain.














