# ngx-imagesloaded

[![NPM Version](https://img.shields.io/npm/v/ngx-imagesloaded.svg?style=flat-square)](https://www.npmjs.com/package/ngx-imagesloaded)
[![NPM Size + Gzip](https://img.shields.io/bundlephobia/minzip/ngx-imagesloaded.svg?style=flat-square)](https://www.npmjs.com/package/ngx-imagesloaded)
[![NPM Downloads](https://img.shields.io/npm/dt/ngx-imagesloaded.svg?style=flat-square)](https://www.npmjs.com/package/ngx-imagesloaded)
[![NPM License](https://img.shields.io/npm/l/ngx-imagesloaded.svg?style=flat-square)](https://www.npmjs.com/package/ngx-imagesloaded)

Angular 2+ wrapper package around [imagesLoaded by Desandro](https://imagesloaded.desandro.com). Detect when images have been loaded. It is forked project. The difference from the original is that directive is used on the collection instead on parent element. Fixed watching event failed, done, progress as well.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Changelog](#changelog)
- [Paperwork](#paperwork)
  - [Contributing](#contributing)
  - [Issue / Feature Request](#issue--feature-request)
  - [Pull Request](#pull-request)
- [Credits](#credits)
- [License](#license)

## Installation

```bash
npm install --save ngx-imagesloaded
```

```bash
yarn add ngx-imagesloaded
```

## Usage

**app.module.ts**

```ts
import { NgModule } from '@angular/core';
import { NgxImagesloadedModule } from 'ngx-imagesloaded';

import { AppComponent } from './app.component';

@NgModule({
  declarations: [ AppComponent ],
  imports: [ NgxImagesloadedModule ],
  bootstrap: [ AppComponent ]
})
export class AppModule { }
```

**app.component.html**

```html
<div class="parent">
  <img *ngFor="let img of imgs" [src]="img.src" imagesLoaded>
</div>
```

### Options

You can pass options input to container element;

```html
<div class="parent">
  <img *ngFor="let img of imgs" [src]="img.src" [options]="{ background: true } imagesLoaded>
</div>
```

or create object inside **app.component.ts** using interface `NgxImagesloadedOptions` and pass to element;

```ts
imgOptions: NgxImagesloadedOptions = {
  background: '.item'
};
```

```html
<div  class="parent">
  <div *ngFor="let item of items" class="item" imagesLoaded [options]="imgOptions">{{ item.id }}</div>
</div>
```

More information about options can be found [here](https://imagesloaded.desandro.com/#background).

### Events

Container element outputs some events;

For example: Triggered after all images have been loaded with at least one broken image;

```html
<div class="parent">
  <img *ngFor="let img of imgs" [src]="img.src" (fail)="handleFail($event)" imagesLoaded>
</div>
```

Full list of events can be found [here](https://imagesloaded.desandro.com/#events).

## Changelog

Please see [Changelog Page](https://github.com/zgabievi/ngx-imagesloaded/releases) for more information what has changed recently.

## Paperwork

### Contributing

Please see [CONTRIBUTING.md](https://github.com/zgabievi/ngx-imagesloaded/blob/master/CONTRIBUTING.md) for details.

### Issue / Feature Request

To submit an issue correctly, please follow [instructions](https://github.com/zgabievi/ngx-imagesloaded/blob/master/.github/ISSUE_TEMPLATE.md#bug-report)

If you have an idea, and you want to request feature, then read [this one](https://github.com/zgabievi/ngx-imagesloaded/blob/master/.github/ISSUE_TEMPLATE.md#feature-request)

### Pull Request

To crearte new pull request and add your piece of work in our project, go through this [steps](https://github.com/zgabievi/ngx-imagesloaded/blob/master/.github/PULL_REQUEST_TEMPLATE.md)

## Credits

- [Zura Gabievi](https://github.com/zgabievi)
- [All contributors](https://github.com/zgabievi/ngx-imagesloaded/graphs/contributors)

## License

The MIT License (MIT). Please see [License file](https://github.com/zgabievi/ngx-imagesloaded/blob/master/LICENSE) for more information.
