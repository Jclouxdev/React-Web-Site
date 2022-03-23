# Build a Fully Responsive Modern UI/UX Webiste in React JS

For this project I am following this [youtube guide](https://www.youtube.com/watch?v=27JtRAI3QO8&ab_channel=Bedimcode).

## 🎉 Initialization of React Project

- `npx create-react-app ./`

The output should be something like this :

```
/gpt3_learning
    |___ /node_modules
    |___ /public
    |___ /src
    |___ package-lock.json
    |___ package.json
```

## 📂 Folders Structure

First we delete the `/src` folder and recreate an empty one.

Inside this new folder we create a `index.js` file.

```
...
    /src
        |___ index.js
...
```

In this file we will initialize our application with the following code :

```js
import React from "react";
import ReactDOM from "react-dom";

import App from "./App";

//The App component will be render inside the div.root
ReactDOM.render(<App />, document.getElementById("root));
```

**Next step** is to create the `App.js` file inside the `/src` folder.

```
...
    /src
        |___ index.js
        |___ App.js
...
```

Inside this file we use `rafce` snippet from ES7 Snipet Extension to generate basics code.

```js
import React from "react";

const App = () => {
  return (
    <div>
      <h1>GPT-3</h1>
    </div>
  );
};

export default App;
```

### Dependencies

For this project we will only use one dependencie, we install it with the following command :

`npm install react-icons`

### Components

We create a `/components` folder inside `/src` folder.

Next we create a folder for each component we will create for the web site.

In thoose components folders we will create **functional component** files and **css** file (named like the parent folder).

We can use again `rafce` to generate code in `.jsx` files and then import the `.css` file with `import "./article.css";`.

```
...
    /src
        |___ /components
            |___ /article
                |___ article.css
                |___ Article.jsx
            |___ /navbar
                |___ navbar.css
                |___ Navbar.jsx
            |___ ...
            |___ index.js
        |___ index.js
        |___ App.js
...
```

**In `/components` folder**, we create an `index.js` file in which we export all of ours components to import them easily later on.

```js
export { default as Article } from "./article/Article";
export { default as Brand } from "./brand/Brand";
export { default as Cta } from "./cta/Cta";
export { default as Feature } from "./feature/Feature";
export { default as Navbar } from "./navbar/Navbar";
```

### Containers

**Containers** are bigger elements usings one or multiple **components**. The folder structure work's the same.

```
...
    /src
        |___ /components
        |___ /containers
            |___ /blog
                |___ blog.css
                |___ Blog.jsx
            |___ /footer
                |___ footer.css
                |___ Footer.jsx
            |___ ...
            |___ index.js
        |___ index.js
        |___ App.js
...
```

We do the same things as **components** with an `index.js`.

## Usings our new components

We import all our new elements in our `App.js` :

```js
import React from "react";

import {
  Footer,
  Blog,
  Possibility,
  Features,
  WhatGPT3,
  Header,
} from "./containers";
import { Cta, Brand, Navbar } from "./components";

const App = () => {
  return (
    <div className="App">
      <div className="gradiant_bg">
        <Navbar />
        <Header />
      </div>
      <Brand />
      <WhatGPT3 />
      <Features />
      <Possibility />
      <Cta />
      <Blog />
      <Footer />
    </div>
  );
};

export default App;
```

## ☀️ Navbar

We create an `/assets` folder in `/src`.

We setup styles for the site :

- `App.css` take all our global CSS
- `index.css` take our css variables

```
    /src
    |___ ...
    |___ App.css
    |___ index.css
```

Import css files in `App.js`

```js
import "./index.css";
import "./App.css";
```

You can found **Navbar** code here :

- [Navbar CSS](src/components/navbar/navbar.css)
- [Navbar JSX](src/components/navbar/Navbar.jsx)

## ☀️ Header

Nothing special with directory structure here, you can just see the code in thooses files :

- [Header CSS](src/containers/header/header.css)
- [Header JSX](src/containers/header/Header.jsx)

## ☀️ Brands

We will use multiples images, so we create a `imports.js` file in the `/brand` folder. The file code :

```js
import google from "../../assets/google.png";
import slack from "../../assets/slack.png";
import atlassian from "../../assets/atlassian.png";
import dropbox from "../../assets/dropbox.png";
import shopify from "../../assets/shopify.png";

export { google, slack, atlassian, dropbox, shopify };
```

Back to `Brand.jsx` :

```js
...
import { google, slack, atlassian, dropbox, shopify } from "./imports";
...
```

Realy small section :

- [Brand CSS](src/components/brand/brand.css)
- [Brand JSX](src/components/brand/brand.jsx)

## ☀️ What Is GPT3

In this section, we are going to re-use the `<Feature />` component.

In the `Feature.jsx` file, we pass 2 arguments in the component, one for the `title` and the other for the `text`.

```js
const Feature = ({ title, text }) => {
  return (
    ...
  );
};
```

We can now give to the component in our `WhatGPT3.jsx` the two arguments to feed him :

```js
<Feature
  title="What is GPT-3"
  text="We so opinion friends me message as delight. Whole front do of plate heard oh ought. His defective nor convinced residence own. Connection has put impossible own apartments boisterous. At jointure ladyship an insisted so humanity he. Friendly bachelor entrance to on by."
/>
```

### Feature Components Files

- [Feature Css](src/components/feature/feature.css)
- [Feature JSX](src/components/feature/feature.jsx)

### What Is GPT-3 Section Files

- [whatGPT3 Css](src/containers/whatGPT3/whatGPT3.css)
- [whatGPT3 JSX](src/containers/whatGPT3/whatGPT3.jsx)
