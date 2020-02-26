# Solutions

## 1. Screen Scaling Issue [easy]

To the `&-price-block-value` selector, I added the following code to add an additional margin when the window screen is between `768 - 1022` pixels. 

```
@media  (min-width: 768px) and (max-width: 1022px) {
  margin-top: 3.5rem;
  margin-left: .5rem;
}
```

In addition I added a specific media query reducing the font size by about ~`30%` for each of the `.prefix`, `.value`, and `.suffix` selectors. 

In order that the texts may fit in the container, I also changed the flex direction in `&-items-container` to `column`.

Finally, I removed the `&-item-inner` because a fixed 270px width is no longer needed. 
  
## 2. Mobile Package Centering [easy]

In order to center align the element, I added an `align-items: center` property to the parent of the blocks, `packages-container`. In addition so that all the package blocks are of equal width I added a `min-width: 366px` property when the window is resized between `500-959` pixels.

## 3. Included Items [easy]

The problem here was that `item` is not a boolean (it's an object) and the check `typeof item === 'boolean'` always returns false. We just need to grab the `included` value from the `item` object and return it's inverse.

## 4. Refactor [normal]

I thought the file was fairly clean. The only thing that was bothering me was the large data object existing in the same file. Usually this data would be fetched from a datastore via an api and it is distracting in the code base. 

## 5. BONUS [hard]

I removed the [vue-lazyload](https://github.com/hilongjw/vue-lazyload#usage) component `lazy-component` and replaced it with a regular `<div>`. Because this component defers loading of the images to the page-load time, it's not being picked up by the `ImagePresenter.vue`.



