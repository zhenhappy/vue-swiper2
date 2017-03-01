[![npm](https://img.shields.io/npm/l/vue-swiper2.svg?maxAge=2592000)](https://raw.githubusercontent.com/zhenhappy/vue-swiper2/master/LICENSE)
[![npm](https://img.shields.io/npm/v/vue-swiper2.svg?maxAge=2592000)](https://www.npmjs.com/package/vue-swiper2)
[![GitHub release](https://img.shields.io/github/release/zhenhappy/vue-swiper2.svg?maxAge=2592000)](https://github.com/zhenhappy/vue-swiper2/releases)
[![GitHub issues](https://img.shields.io/github/issues/zhenhappy/vue-swiper2.svg?maxAge=2592000)](https://github.com/zhenhappy/vue-swiper2/issues)
[![GitHub stars](https://img.shields.io/github/stars/zhenhappy/vue-swiper2.svg?style=social&label=Star&maxAge=2592000)](https://github.com/zhenhappy/vue-swiper2) 

[![NPM](https://nodei.co/npm/vue-swiper2.png?downloads=true&downloadRank=true)](https://nodei.co/npm/vue-swiper2/)

# vue-swiper
Swiper component for Vue 2.0. Easy to use.  
Fork from [https://github.com/weilao/vue-swiper](https://github.com/weilao/vue-swiper)

## Examples
[basic demo](http://zhenhappy.github.io/vue-swiper2/demo)

[webpack ES2015 demo](http://www.webpackbin.com/4kbKGs97b)

## Install
```
npm i vue-swiper2 -S
```

## Usage

```js
import Vue from 'vue'
import Swiper from 'vue-swiper2'

new Vue({
    el: 'body',
    components: {Swiper},
    methods: {
        onSlideChangeStart (currentPage) {
            console.log('onSlideChangeStart', currentPage);
        },
        onSlideChangeEnd (currentPage) {
            console.log('onSlideChangeEnd', currentPage);
        }
    }
});
```

```html
<swiper ref="swiper"
        direction="horizontal"
        :mousewheel-control="true"
        :performance-mode="false"
        :pagination-visible="true"
        :pagination-clickable="true"
        :loop=“true”
        @slide-change-start="onSlideChangeStart"
        @slide-change-end="onSlideChangeEnd">
    <div>Page 1</div>
    <div>Page 2</div>
    <div>Page 3</div>
</swiper>
```

## Api
### Properties
| Name                 | Type      | Default      | Description                                                        |
|----------------------|-----------|--------------|--------------------------------------------------------------------|
| direction            | `String`  | `"vertical"` | Could be 'horizontal' or 'vertical' (for vertical slider).         |
| mousewheel-control   | `Boolean` | `true`       | Set to true to enable navigation through slides using mouse wheel. |
| pagination-visible   | `Boolean` | `false`      | Toggle (hide/true) pagination container visibility when click on Slider's container    |
| pagination-clickable | `Boolean` | `false`      | If true then clicking on pagination button will cause transition to appropriate slide. |
| performace-mode      | `Boolean` | `false`      | Disable advance effect for better performance.                     |
| loop                 | `Boolean` | `false`      | Set to true to enable continuous loop mode                         |


### Methods
| Method            | Description              |
|-------------------|--------------------------|
| next()            | Go next page.            |
| prev()            | Go previous page.        |
| setPage(`Number`) | Set current page number. |

### Events
| Name                            | Parameters | Description                                                                                                                                                  |
|--------------------|------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| slide-change-start | `pageNumber`     | Fire in the beginning of animation to other slide (next or previous).                                                                                        |
| slide-change-end   | `pageNumber`     | Will be fired after animation to other slide (next or previous).                                                                                             |
| slide-revert-start | `pageNumber`     | Fire in the beginning of animation to revert slide (no change).                                                                                              |
| slide-revert-end   | `pageNumber`     | Will be fired after animation to revert slide (no change).                                                                                                   |
| slider-move        | `offset`         | Callback function, will be executed when user touch and move finger over Swiper and move it. Receives swiper instance and 'touchmove' event as an arguments. |