# chord-illustrator [![NPM version][npm-image]][npm-url] [![Build Status][travis-image]][travis-url] [![Dependency Status][daviddm-image]][daviddm-url]
> SVG based library which illustrates finger positions of a guitar chord on a fretboard.

> _based on [guitar-js](https://www.npmjs.com/package/guitar-js) (Fomin Sergey)_

## Installation
```sh
$ npm install --save chord-illustrator
```

## Usage
>*illustrates B minor*
```js
// import chord-illustrator & xmldom
const ChordIllustrator = require('chord-illustrator');
const DOMParser = require('xmldom').DOMParser;

// prepare html objects
// https://www.w3.org/DOM/
const document = new DOMParser().parseFromString('<html></html>');

// 
const ci = new ChordIllustrator(document.createElement('div'))

const svg = ci.make({
    name: 'Bm',
    mutedStrings: ['yes'],
    fingering: [
        {
            fret: 1,
            barre: {from: 1, to: 5}
        },
        {fret: 2, string: 2},
        {fret: 3, string: 3},
        {fret: 3, string: 4}
    ]
});

console.log('HTML output', svg.toString());
```

> XML generated
```xhtml
<svg height="440" viewbox="0 0 215 133" xmlns="http://www.w3.org/2000/svg">
    <rect x="25" y="27" height="100" width="180" stroke="rgb(0, 0, 0)" stroke-width="1" fill="rgb(255, 255, 255)"/>
    <line x1="85" y1="27" x2="85" y2="127" stroke="rgb(0, 0, 0)" stroke-width="1"/>
    <line x1="145" y1="27" x2="145" y2="127" stroke="rgb(0, 0, 0)" stroke-width="1"/>
    <line x1="205" y1="27" x2="205" y2="127" stroke="rgb(0, 0, 0)" stroke-width="1"/>
    <line x1="25" y1="47" x2="205" y2="47" stroke="rgb(0, 0, 0)" stroke-width="1"/>
    <line x1="25" y1="67" x2="205" y2="67" stroke="rgb(0, 0, 0)" stroke-width="1"/>
    <line x1="25" y1="87" x2="205" y2="87" stroke="rgb(0, 0, 0)" stroke-width="1"/>
    <line x1="25" y1="107" x2="205" y2="107" stroke="rgb(0, 0, 0)" stroke-width="1"/>
    <line x1="25" y1="127" x2="205" y2="127" stroke="rgb(0, 0, 0)" stroke-width="1"/>
    <circle cx="15" cy="27" r="5" stroke="rgb(0, 0, 0)" stroke-width="1" fill="rgb(255, 255, 255)"/>
    <circle cx="15" cy="47" r="5" stroke="rgb(0, 0, 0)" stroke-width="1" fill="rgb(255, 255, 255)"/>
    <circle cx="15" cy="67" r="5" stroke="rgb(0, 0, 0)" stroke-width="1" fill="rgb(255, 255, 255)"/>
    <circle cx="15" cy="87" r="5" stroke="rgb(0, 0, 0)" stroke-width="1" fill="rgb(255, 255, 255)"/>
    <circle cx="15" cy="107" r="5" stroke="rgb(0, 0, 0)" stroke-width="1" fill="rgb(255, 255, 255)"/>
    <line x1="10" y1="122" x2="20" y2="132" stroke="rgb(0, 0, 0)" stroke-width="1"/>
    <line x1="20" y1="122" x2="10" y2="132" stroke="rgb(0, 0, 0)" stroke-width="1"/>
    <circle cx="55" cy="27" r="5" stroke="rgb(0, 0, 0)" stroke-width="1" fill="rgb(0, 0, 0)"/>
    <circle cx="55" cy="107" r="5" stroke="rgb(0, 0, 0)" stroke-width="1" fill="rgb(0, 0, 0)"/>
    <rect x="50" y="27" height="80" width="10" stroke="rgb(0, 0, 0)" stroke-width="1" fill="rgb(0, 0, 0)"/>
    <circle cx="115" cy="47" r="5" stroke="rgb(0, 0, 0)" stroke-width="1" fill="rgb(0, 0, 0)"/>
    <circle cx="175" cy="67" r="5" stroke="rgb(0, 0, 0)" stroke-width="1" fill="rgb(0, 0, 0)"/>
    <circle cx="175" cy="87" r="5" stroke="rgb(0, 0, 0)" stroke-width="1" fill="rgb(0, 0, 0)"/>
</svg>
```
> in browser

![sometext](https://image.ibb.co/k9XznU/Screen_Shot_2018_09_23_at_18_33_23.png)

#### release notes
> v1.1.0
- moved width & height to viewBox attribute for svg container, which allows the fields to be used as input
- added/changed new methods: **setContainer**, **setHeight**, **make**

> #Docs

#### .setContainer(HTMLElement)
- set the container where output will be generated.

#### .make(name: string, fingering: array, mutedStrings: array)

>##### @param(name: string)
> chord name/title

>##### @param(fingering: string)
>

>##### @param(mutedStrings: string)
>from E4 to E6\
array of max 6 items filled with ”yes/no”\
if not specified, value will default to “open”


## License

Apache-2.0 © [Alexandru Calin](https://alexandrucalin.me/)


[npm-image]: https://badge.fury.io/js/chord-illustrator.svg
[npm-url]: https://npmjs.org/package/chord-illustrator
[travis-image]: https://travis-ci.org/calinalexandru/chord-illustrator.svg?branch=master
[travis-url]: https://travis-ci.org/calinalexandru/chord-illustrator
[daviddm-image]: https://david-dm.org/calinalexandru/chord-illustrator.svg?theme=shields.io
[daviddm-url]: https://david-dm.org/calinalexandru/chord-illustrator
