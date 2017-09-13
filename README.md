# French Bad Words List (french-badwords-list)

 [![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT) [![Build Status](https://travis-ci.org/darwiin/french-badwords-list.svg?branch=master)](https://travis-ci.org/darwiin/french-badwords-list) [![Coverage Status](https://coveralls.io/repos/github/darwiin/french-badwords-list/badge.svg?branch=master)](https://coveralls.io/github/darwiin/french-badwords-list?branch=master)


## Synopsis

A highly consumable list of bad (profanity) french words based on the list found in [Wiktionary.org](https://fr.wiktionary.org/w/index.php?title=Cat%C3%A9gorie:Insultes_en_fran%C3%A7ais&pageuntil=mongol+a+batteries%0Amongol+%C3%A0+batteries#mw-pages)

[![NPM](https://nodei.co/npm/french-badwords-list.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/french-badwords-list/) [![NPM](https://nodei.co/npm-dl/french-badwords-list.png?height=2)](https://nodei.co/npm/french-badwords-list/)

Inspired by [badwords-list](https://github.com/MauriceButler/badwords)

## Code Example

This bad (profanity) french words list can be used with [bad-words](https://www.npmjs.com/package/bad-words) or [leo-profanity](https://www.npmjs.com/package/leo-profanity) for example. (If you want to add your filter module don't hesitate to create a pull request on the readme).

```
var list = require('french-badwords-list'),
	array = list.array,
	object = list.object,
	regex = list.regex;
```

### with leo-profanity

```
	// Usage example with leo-profanity
	var leoProfanity = require('leo-profanity');
	var frenchBadwordsList = require('../liste-gros-mots');

	// Only keep french badwords
	leoProfanity.clearList();
	leoProfanity.add(frenchBadwordsList.array);

	// output: true
	console.log(leoProfanity.check('Bordel de merde'));

	// output: ****** de *****
	console.log(leoProfanity.clean('Bordel de merde'));

	// output: ****** de *****
	console.log(leoProfanity.clean('B0rdel de m3rd3'));
```

### with bad-words

```
	// Usage example with leo-profanity
	var BadWords = require('bad-words');
	const frenchBadwords = require('french-badwords-list');

	// Only keep french badwords
	var badwords = new BadWords({ placeHolder: 'x', emptyList: true}); 
	badwords.addWords(frenchBadwordsList.array);
  
	// output: xxxxxx de xxxxx
	badwords.clean('B0rdel de m3rd3'));
```

## Motivation

This project was created to be used with badwords or leo-profanity nodes modules as a source for french bad words to filter.

## Installation

```
npm install french-badwords-list
```

## Tests

#### Requires
- Mocha
- better-assert

#### Run
```
npm test
```

## Release Notes
- v1.0.0 / Sep 07 2017: Initial publish
- v1.0.1 / Sep 13 2017: Updated french bad words list

## License

The MIT License (MIT)

Copyright (c) 2013 Maurice Butler

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.