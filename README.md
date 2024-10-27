# react-before-after-slider-component

An intuitive React component for creating interactive before-and-after sliders, perfect for comparing images with transformations, such as background removal, retouching, or other edits. Forked from [smeleshkin/react-before-after-slider-component](https://github.com/smeleshkin/react-before-after-slider-component).

### Key Features
- **Responsive**: Fits both mobile and desktop screens
- **Customizable**: Adjust dimensions, initial slider position, and styles
- **Touch-Friendly**: Supports smooth interaction on mobile devices
- **Ideal for Visual Comparisons**: Show transformations like background removal, image editing, or design changes

[![screencast demo](./screencast.gif)](./screencast.gif)


## Demo
https://smeleshkin.github.io/react-before-after-slider-component/
## Build

```
npm run build:npm
```
## Basic usage
```
npm install react-before-after-slider-component --save
```

Then use it in your app:
```javascript
import React from 'react';
import ReactBeforeSliderComponent from 'react-before-after-slider-component';
import 'react-before-after-slider-component/dist/build.css';

const FIRST_IMAGE = {
  imageUrl: 'https://example.com/path/to/original-image.jpg'
};
const SECOND_IMAGE = {
  imageUrl: 'https://example.com/path/to/edited-image.jpg'
};

function App() {
  return (
    <ReactBeforeSliderComponent
      firstImage={FIRST_IMAGE}
      secondImage={SECOND_IMAGE}
    />
  );
}
```
## Props

| Attribute                 | Required                         | Type                          | Default | Description   |
|---------------------------|----------------------------------|-------------------------------|---------|-------------------------------|
| `firstImage`              | true                             | Image                         |         | Image object with source url. |
| `secondImage`             | true                             | Image                         |         | Image object with source url. |
| `delimiterColor`          | false                            | string                        | #fff    | Custom delimiter background color. |
| `currentPercentPosition`  | false                            | number                        | 50      | Start delimiter position. Or also the current position, if it will change in parent. |
| `className`               | false                            | string                        |         | Custom classname. |
| `withResizeFeel`          | false                            | boolean                       | true    | Feeling to window resizing. |
| `onReady`                 | false                            | function                      |         | On slider ready callback. |
| `onVisible`               | false                            | function                      |         | On slider visible in viewport callback. |
| `onChangePercentPosition` | false                            | (newPosition: number) => void |         | On delimiter position update callback. Has new position parameter. |
| `feelsOnlyTheDelimiter`   | false                            | boolean                       | false   | Only the separator feels clicks. Not any zone of the component. |
| `delimiterIconStyles`     | false                            | React.CSSProperties           |         | Custom styles of delimiter icon. E.g. for a logo. See "Custom logo example". |
| `onChangeMode`            | false                            | (newMode: MODE) => void       |         | Callback when the slider mode changes. Can be used to disable page scrolling on touch devices while sliding. |

## Specific Types

```ts
interface Image {
    imageUrl: string,
    alt?: string,
}

export enum MODE {
    MOVE = 'move', // Moving the slider
    DEFAULT = 'default', // Resting state
}
```

## Custom logo example
```ts
// Pass this as a delimiterIconStyles property
const delimiterIconStyles = {
   width: '50px',
   height: '50px',
   backgroundSize: 'cover',
   borderRadius: 'none',
   backgroundImage: 'url(<some-path-here>)'
}

```
