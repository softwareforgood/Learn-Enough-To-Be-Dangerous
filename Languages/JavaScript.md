# Learn JavaScript

The internet couldn't function without it.

The [JavaScript Basics](https://www.theodinproject.com/paths/foundations/courses/foundations#javascript-basics) is a great tutorial to familiarize yourself with this language.

## Key points

- Object oriented
- Used in ever browser
- Libraries are called [packages](https://docs.npmjs.com/about-packages-and-modules)
- Leading utility for organizing packages is called [npm](https://www.npmjs.com)
- A second leading utility for organizing packages is called [yarn](https://yarnpkg.com/en/)
- A leading view library is called [ReactJS](https://reactjs.org/)
- ReactJS has integrations for web and [mobile development](https://reactnative.dev/)
- Leading web development framework is Angular

## Nodejs

[Nodejs](https://nodejs.org/en/) is a JavaScript run-time environment that allows you to execute JavaScript code outside of your browser. Think of it as a utility that you will use to build other things.

It's a deep and complex subject that you might want to learn all about. Here, you just need to know how to use it. It will help you to download JavaScript libraries and stuff.

## Environment

### Installing Node

It's pretty useful to use a version manager when using Node because different projects may only run on certain versions of Node and you may need to switch depending on what you're working on. [nvm](https://github.com/nvm-sh/nvm#intro) is a useful tool available for Linux/OSX. You can find other tools that are available [here](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm#using-a-node-version-manager-to-install-nodejs-and-npm).

## Preliminary steps

- Familiarize yourself with [documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

### Basic JavaScript

1. Every browser relies on it.

```javascript
var add = function (a, b) {
  return a + b;
};
```

### ES2015

1. ES 5 is the version or specification of JavaScript that is currently used in all browsers.
2. ES2015 (a.k.a. ES6) is the version of JavaScript that the industry is in the process of adopting and incorporating.
   ES2015 is a pseudonym for the latest version of the JavaScript programming language to be approved by ECMA International, the standards group responsible for vetting and approving different versions of the language. In June of 2015, ECMA International approved the 6th edition of the language. The name, ES2015, is given because the latest version of JavaScript is identified as the 2015 version of ECMAScript (an alternative name for JavaScript).

ES2015 isn't introducing anything other than improvements to the JavaScript language and a few new features. It is not an alternative syntax or language like CoffeeScript or TypeScript. It's good ol' fashioned JavaScript. The reason so many people are excited is that this version introduces a lot of much-needed improvements to the language. [source](https://themeteorchef.com/blog/what-is-es2015)

#### Example

```javascript
const add = (a, b) => {
  return a + b;
};
```

### jQuery

- [Document Ready](https://learn.jquery.com/using-jquery-core/document-ready/)
- Makes [DOM](https://www.w3schools.com/js/js_htmldom.asp) manipulation easier
