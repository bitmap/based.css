# Based.css

Based is a barebones CSS framework for prototype or production. Based features an extensive flexbox grid system and OOCSS classes that don't make assumptions about your application's styles or override any browser defaults.

## Docs
[Read up on Based](http://cabe.io/based.css).

## Installation

Based can be installed with your favorite package manager:

- npm `npm install based.css --save`
- Yarn `yarn add based.css`

## BYO Based

(Build your own Based). Don't like something? Fix it. Based is built with [Sass](http://sass-lang.com). Clone this repo and you can tweak anything. Some setting like grid columns, base padding/margins, type-size, breakpoints, etc. can be easily adjusted in `src/_config.scss`.

The command `npm run build` will build you a custom version of Based.

## Based is Big
Based is barebones, but it's not light. It's ~33kb minified. There's probably a lot of CSS you won't use. Using something like [uncss](https://github.com/giakki/uncss) is *highly* recommended if you're building something that needs to remain lean.
