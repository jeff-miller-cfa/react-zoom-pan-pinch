# react-zoom-pan-pinch

<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->[![All Contributors](https://img.shields.io/badge/all_contributors-4-orange.svg?style=flat-square)](#contributors-)<!-- ALL-CONTRIBUTORS-BADGE:END -->

[![NPM](https://img.shields.io/npm/v/react-zoom-pan-pinch.svg)](https://www.npmjs.com/package/react-zoom-pan-pinch) ![npm bundle size](https://img.shields.io/bundlephobia/minzip/react-zoom-pan-pinch) [![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com) [![Package Quality](https://npm.packagequality.com/shield/react-zoom-pan-pinch.svg)](https://packagequality.com/#?package=react-zoom-pan-pinch) ![NPM](https://img.shields.io/npm/l/react-zoom-pan-pinch) ![npm](https://img.shields.io/npm/dm/react-zoom-pan-pinch) ![GitHub stars](https://img.shields.io/github/stars/prc5/react-zoom-pan-pinch?style=social)

> Super fast and light react npm package for zooming, panning and pinching html elements in easy way

## Features

- :rocket: Fast and easy to use
- :factory: Light, without external dependencies
- :gem: Mobile gestures, touchpad gestures and desktop mouse events support
- :gift: Powerful context usage, which gives you a lot of freedom
- :wrench: Highly customizable
- :crown: Animations and many options

## DEMO

[DEMO EXAMPLE](https://prc5.github.io/react-zoom-pan-pinch/)

## Install

```bash
npm install --save react-zoom-pan-pinch
```

or

```bash
yarn add react-zoom-pan-pinch
```

## Usage

```jsx
import React, { Component } from "react";

import { TransformWrapper, TransformComponent } from "react-zoom-pan-pinch";

class Example extends Component {
  render() {
    return (
      <TransformWrapper>
        <TransformComponent>
          <img src="image.jpg" alt="test" />
        </TransformComponent>
      </TransformWrapper>
    );
  }
}
```

or

```jsx
import React, { Component } from "react";

import { TransformWrapper, TransformComponent } from "react-zoom-pan-pinch";

class Example extends Component {
  render() {
    return (
      <TransformWrapper defaultScale={1} defaultPositionX={200} defaultPositionY={100}>
        {({ zoomIn, zoomOut, resetTransform, ...rest }) => (
          <React.Fragment>
            <div className="tools">
              <button onClick={zoomIn}>+</button>
              <button onClick={zoomOut}>-</button>
              <button onClick={resetTransform}>x</button>
            </div>
            <TransformComponent>
              <img src="image.jpg" alt="test" />
              <div>Some text</div>
            </TransformComponent>
          </React.Fragment>
        )}
      </TransformWrapper>
    );
  }
}
```

## Props of TransformWrapper

| Props                   | Default  |           Type |
| :---------------------- | :------: | -------------: |
| isCentered              |   true   |        Boolean |
| limitToBounds           |   true   |        Boolean |
| limitToWrapperBounds    |  false   |        Boolean |
| disabled                |  false   |        Boolean |
| transformEnabled        |   true   |        Boolean |
| positionX               |    0     |         Number |
| positionY               |    0     |         Number |
| maxPositionX            |   null   | Number or null |
| minPositionX            |   null   | Number or null |
| maxPositionY            |   null   | Number or null |
| minPositionY            |   null   | Number or null |
| zoomingEnabled          |   true   |        Boolean |
| scale                   |    1     |         Number |
| maxScale                |    8     | Number or null |
| minScale                |    1     | Number or null |
| scaleAnimationPadding   |   0.15   |         Number |
| enableWheel             |   true   |        Boolean |
| enableTouchPadPinch     |   true   |        Boolean |
| wheelStep               |    4     |         Number |
| limitToWrapperOnWheel   |  false   |        Boolean |
| pinchEnabled            |   true   |        Boolean |
| pinchSensitivity        |    1     |         Number |
| panningEnabled          |   true   |        Boolean |
| lockAxisX               |  false   |        Boolean |
| lockAxisY               |  false   |        Boolean |
| enableVelocity          |   true   |        Boolean |
| velocityTimeBasedOnMove |   true   |        Boolean |
| minVelocity             |   1.6    |         Number |
| minVelocityScale        |    1     |         Number |
| velocityAnimationSpeed  |   1800   |         Number |
| velocitySensitivity     |    1     |         Number |
| dbClickMode             | "zoomIn" |         String |
| dbClickStep             |    40    |         Number |
| zoomInStep              |    40    |         Number |
| zoomOutStep             |    40    |         Number |
| zoomInAnimationSpeed    |   200    |         Number |
| zoomOutAnimationSpeed   |   200    |         Number |
| dbClickAnimationSpeed   |   200    |         Number |
| resetAnimationSpeed     |   200    |         Number |
| paddingAnimationSpeed   |   200    |         Number |
| onWheelStart            |   null   |       Function |
| onWheel                 |   null   |       Function |
| onWheelStop             |   null   |       Function |
| onPanningStart          |   null   |       Function |
| onPanning               |   null   |       Function |
| onPanningStop           |   null   |       Function |
| onPinchingStart         |   null   |       Function |
| onPinching              |   null   |       Function |
| onPinchingStop          |   null   |       Function |
| onZoomChange            |   null   |       Function |
| enablePadding           |   true   |        Boolean |
| enablePanPadding        |   true   |        Boolean |

## Values returned from TransformWrapper component

| Value                                     | Description                                                                                            |      Type      |
| :---------------------------------------- | :----------------------------------------------------------------------------------------------------- | :------------: |
| minVelocity                               | Minimum mouse velocity which will be animated after panning is done                                    |     Number     |
| minVelocityScale                          | Velocity will be disabled if value is equal or lower than given value                                  |     Number     |
| velocityTimeBasedOnMove                   | Velocity duration is based on the mouse move - the longer the movement, the longer the animation lasts |    Boolean     |
| limitToWrapperBounds                      | Enables panning when zoom is lower than 1, and limit it to the wrapper bounds                          |    Boolean     |
| limitToWrapperOnWheel                     | Zoomed object is always inside wrapper if limitBounds is activated                                     |    Boolean     |
| limitToBounds                             | Limit zooming and panning to wrapper boundaries                                                        |    Boolean     |
| setScale(scale)                           | Sets scale                                                                                             |     Number     |
| setPositionX(positionX)                   | Sets position x                                                                                        |     Number     |
| setPositionY(positionY)                   | Sets position y                                                                                        |     Number     |
| zoomIn()                                  | Zooming in function, used for controls button                                                          |      ---       |
| zoomOut()                                 | Zooming out function, used for controls button                                                         |      ---       |
| setTransform(positionX, positionY, scale) | Sets transformations of content                                                                        | Number or null |
| resetTransform()                          | Reset transformations to the initial values                                                            |     Number     |
| dbClickMode                               | Available modes: "zoomIn", "zoomOut", "reset"                                                          |     String     |

## License

MIT © [prc5](https://github.com/prc5)

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="http://maciejpyrc.pl"><img src="https://avatars3.githubusercontent.com/u/20928302?v=4" width="80px;" alt="Maciej Pyrc"/><br /><sub><b>Maciej Pyrc</b></sub></a><br /><a href="#review-prc5" title="Reviewed Pull Requests">👀</a> <a href="https://github.com/prc5/react-zoom-pan-pinch/commits?author=prc5" title="Code">💻</a> <a href="#infra-prc5" title="Infrastructure (Hosting, Build-Tools, etc)">🚇</a> <a href="#maintenance-prc5" title="Maintenance">🚧</a> <a href="#example-prc5" title="Examples">💡</a> <a href="#question-prc5" title="Answering Questions">💬</a></td>
    <td align="center"><a href="https://github.com/shaneeza"><img src="https://avatars2.githubusercontent.com/u/5740159?v=4" width="80px;" alt="Shaneeza"/><br /><sub><b>Shaneeza</b></sub></a><br /><a href="https://github.com/prc5/react-zoom-pan-pinch/issues?q=author%3Ashaneeza" title="Bug reports">🐛</a></td>
    <td align="center"><a href="https://github.com/gabrielfmp"><img src="https://avatars2.githubusercontent.com/u/36622624?v=4" width="80px;" alt="gabrielfmp"/><br /><sub><b>gabrielfmp</b></sub></a><br /><a href="https://github.com/prc5/react-zoom-pan-pinch/commits?author=gabrielfmp" title="Code">💻</a></td>
    <td align="center"><a href="https://github.com/pablovegau"><img src="https://avatars1.githubusercontent.com/u/20138953?v=4" width="80px;" alt="Pablo Vega Uceta"/><br /><sub><b>Pablo Vega Uceta</b></sub></a><br /><a href="https://github.com/prc5/react-zoom-pan-pinch/commits?author=pablovegau" title="Code">💻</a></td>
  </tr>
</table>

<!-- markdownlint-enable -->
<!-- prettier-ignore-end -->
<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!