Create a README with the following items:

Description of the problem and how you solved it.
The reasoning behind your decisions.
Any other information you believe is necessary for us to know about the issue/solution.

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

## 3. Included Items [easy]

## 4. Refactor [normal]

## 5. BONUS [hard]



