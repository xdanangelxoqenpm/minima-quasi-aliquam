# @xdanangelxoqenpm/minima-quasi-aliquam
Lightweight util for generating random sentences, paragraphs and articles in English. Inspired by [Sentencer](https://github.com/kylestetz/Sentencer) and [metaphorpsum.com](http://metaphorpsum.com/).

[![NPM](https://badge.fury.io/js/@xdanangelxoqenpm/minima-quasi-aliquam.svg)](https://badge.fury.io/js/@xdanangelxoqenpm/minima-quasi-aliquam)
[![CI test](https://github.com/xdanangelxoqenpm/minima-quasi-aliquam/workflows/ci-test/badge.svg)](https://github.com/xdanangelxoqenpm/minima-quasi-aliquam/actions)
[![Coverage Status](https://coveralls.io/repos/github/ndaidong/@xdanangelxoqenpm/minima-quasi-aliquam/badge.svg)](https://coveralls.io/github/ndaidong/@xdanangelxoqenpm/minima-quasi-aliquam)
![CodeQL](https://github.com/xdanangelxoqenpm/minima-quasi-aliquam/workflows/CodeQL/badge.svg)

# Demo

- [Want to see how it works?](https://ndaidong.github.io/@xdanangelxoqenpm/minima-quasi-aliquam/)

## Setup

- Node.js

  ```bash
  npm i @xdanangelxoqenpm/minima-quasi-aliquam

  # pnpm
  pnpm i @xdanangelxoqenpm/minima-quasi-aliquam

  # yarn
  yarn add @xdanangelxoqenpm/minima-quasi-aliquam
  ```

- CDN

  - ES6 Module: [@xdanangelxoqenpm/minima-quasi-aliquam.esm.js](https://unpkg.com/@xdanangelxoqenpm/minima-quasi-aliquam/dist/@xdanangelxoqenpm/minima-quasi-aliquam.esm.js)
  - CommonJS: [@xdanangelxoqenpm/minima-quasi-aliquam.js](https://unpkg.com/@xdanangelxoqenpm/minima-quasi-aliquam/dist/cjs/@xdanangelxoqenpm/minima-quasi-aliquam.js)
  - For old browsers: [@xdanangelxoqenpm/minima-quasi-aliquam.min.js](https://unpkg.com/@xdanangelxoqenpm/minima-quasi-aliquam/dist/@xdanangelxoqenpm/minima-quasi-aliquam.min.js)


## Usage

### Node.js:

```js
import {
  sentence
} from '@xdanangelxoqenpm/minima-quasi-aliquam'

// with CommonJS environment
// const { sentence } = require('@xdanangelxoqenpm/minima-quasi-aliquam/dist/cjs/@xdanangelxoqenpm/minima-quasi-aliquam.js')

sentence()
```

### Browsers:

Currently, ECMAScript modules work fine on almost all browsers:

```html
<script type="module">
import { sentence } from 'https://unpkg.com/@xdanangelxoqenpm/minima-quasi-aliquam/dist/@xdanangelxoqenpm/minima-quasi-aliquam.esm.js'
console.log(sentence())
</script>
```

With outdated browsers, we can use the traditional method:

```html
<script type="text/javascript" src="https://unpkg.com/@xdanangelxoqenpm/minima-quasi-aliquam/dist/@xdanangelxoqenpm/minima-quasi-aliquam.min.js"></script>

<script>
console.log(window.@xdanangelxoqenpm/minima-quasi-aliquam.sentence())
</script>
```

## APIs

 - `.sentence()`
 - `.paragraph([Number totalSentences])`
 - `.article([Number totalParagraphs])`
 - `.addNouns(Array nouns)`
 - `.addAdjectives(Array adjectives)`
 - `.addTemplates(Array sentenceTemplates)`
 - `.setNouns(Array nouns)`
 - `.setAdjectives(Array adjectives)`
 - `.setTemplates(Array sentenceTemplates)`
 - `.getNouns()`
 - `.getAdjectives()`
 - `.getTemplates()`
 - `.lorem([Number min [, Number max]])`


As their name suggests, we have 4 groups of methods:

- `sentence()`, `paragraph()`, `article()`: generate text by given grammatical unit
- `addNouns()`, `addAdjectives()`, `addTemplates()`: add more samples to current sample set
- `setNouns()`, `setAdjectives()`, `setTemplates()`: replace current sample set with new ones
- `getNouns()`, `getAdjectives()`, `getTemplates()`: get current sample set


The `set*` and `get*` methods were added in v2.2.3 to help you customize your sample data.

In addition, we've added `lorem()` method since v3.0.5 to generate lorem ipsum text.

### Template

If you want to add more kinds of sentences, just use the `.addTemplates()` method; it expects a list of sentence templates.
Each sentence template is an English sentence, containing placeholders that can be replaced with any alternative word.

For example:

```js
import {
  addTemplates
} from '@xdanangelxoqenpm/minima-quasi-aliquam'

const templates = [
  '{{a_noun}} is {{a_noun}} from the right perspective',
  'the {{noun}} of {{a_noun}} becomes {{an_adjective}} {{noun}}'
]

addTemplates(templates)
```

Here are the available placeholders:

- `noun`
- `nouns`
- `a_noun`
- `adjective`
- `an_adjective`


### Lorem ipsum

Syntax:

```js
lorem() // generate a random phrase with length from 2 to 24 words of lorem ipsum
lorem(Number min) // set the minimum number of words
lorem(Number min, Number max)// set the minimum/maximum number of words
```

Example:

```js
import { lorem } from '@xdanangelxoqenpm/minima-quasi-aliquam'

const phrase = lorem()
console.log(phrase) // => nisi blandit feugiat tempus imperdiet etiam eu mus augue
```

## Test

```bash
git clone https://github.com/xdanangelxoqenpm/minima-quasi-aliquam.git
cd @xdanangelxoqenpm/minima-quasi-aliquam
npm install
npm test
```

# License

The MIT License (MIT)
