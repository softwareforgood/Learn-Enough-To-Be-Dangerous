# Learn JavaScript

The internet couldn't function without it.

The [JavaScript Basics](https://www.theodinproject.com/paths/foundations/courses/foundations#javascript-basics) is a great tutorial to familiarize yourself with this language.

## Key points

- Object oriented
- Used in every browser
- Libraries are called [packages](https://docs.npmjs.com/about-packages-and-modules), and are generally installed from [npm](https://www.npmjs.com), either using `npm` itself, or using [yarn](https://yarnpkg.com/en/)
- Some of the most popular front end frameworks are [ReactJS](https://reactjs.org/) (ok, technically not a framework), [Angular](https://angular.io/), and [Vue](https://vuejs.org/)

## Nodejs

[Nodejs](https://nodejs.org/en/) is a JavaScript run-time environment that allows you to execute JavaScript code outside of your browser. Think of it as a utility that you will use to build other things. It is also used, along with tools like [ExpressJS](https://expressjs.com/) or [NextJS](https://nextjs.org/), to write server code in JavaScript.

It's a deep and complex subject that you might want to learn all about. Here, you just need to know how to use it. It will help you to download JavaScript libraries and stuff.

## Environment

### Installing Node

It's pretty useful to use a version manager when using Node because different projects may only run on certain versions of Node and you may need to switch depending on what you're working on. [nvm](https://github.com/nvm-sh/nvm#intro) is a useful tool available for Linux/OSX. You can find other tools that are available [here](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm#using-a-node-version-manager-to-install-nodejs-and-npm).

## Preliminary steps

- Familiarize yourself with [documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- [Eloquent JavaScript](https://eloquentjavascript.net) is a great free online, interactive book that starts from the beginning, teaching a lot of basic programming concepts. This is great if you're just starting out, but if you already know other languages though, you may find a higher level resource that compares how things work in JavaScript to how they work in something you already know more valuable.

### JavaScript Versions

1. ES5 is the version of JavaScript supported in all browsers, but lots of newer features exist in newer versions and are broadly supported.
2. Most projects are written in newer versions and compiled down to older versions as needed using tools like [Babel](https://babeljs.io/) depending on what browsers need to be supported.
3. [Can I Use](https://caniuse.com) is a good resource to figure out where the specific feature of JavaScript, HTML, or CSS is supported.

#### Both of these are valid JavaScript, the second is just a newer syntax

```javascript
var add = function (a, b) {
  return a + b
}
```

```javascript
const add = (a, b) => a + b
```
