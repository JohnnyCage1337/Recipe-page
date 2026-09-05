# Frontend Mentor - Recipe page solution

This is a solution to the [Recipe page challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/recipe-page-KiTsR8QQKm). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)



## Overview

### The challenge

The challenge is to build out this recipe page and get it looking as close to the design as possible. Users should be able to see a responsive layout that works well on different screen sizes.

### Screenshot

**Note:** The screenshots below are of my final solution. I have replaced the original design files to show the result of my work.

#### Desktop
![](./design/desktop-solution.png)

#### Mobile
![](./design/mobile-solution.png)

### Links

- Solution URL: [Github](https://github.com/JohnnyCage1337/Recipe-page)
- Live Site URL: [Github Pages](https://johnnycage1337.github.io/Recipe-page/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Relative and absolute positioning to create custom bullet points

### What I learned

#### HTML
##### A fully semantic HTML approach
- Using the `<dl>` (Description List) element for key-value information.
- Using the `<time>` element for date and time values.
```html
<section class="preparation_container">
  <h2 class="preparation_container__heading">Preparation time</h2>
  <dl class="preparation_container__list">
    <div class="preparation_container__list__row">
      <dt class="preparation_container__list__term">Total</dt>
      <dd class="preparation_container__list__def">Approximately <time datetime="PT10M">10 minutes</time></dd>
    </div>
    ...
  </dl>
</section>
```
- Using `<hr>` to create a thematic break between different sections of the recipe.
- Using the `<b>` tag to draw attention to the title of an instruction step. This is useful for styling when you want to make something visually stand out without giving it strong semantic importance, unlike the `<strong>` tag.
```html
<li class="instructions_container__list__item">
  <p><b>Fold and serve</b> As the omelette continues to cook...</p>
</li>
```
- Using the `<section>` element to group related content on the recipe page.
- Using the `<abbr>` tag for abbreviations.


#### CSS
- Setting a top margin for all direct children of a container except the first one.
```css
.recipe_container > * + * {
  margin-top: var(--sp-400);
}
```

##### Making the card responsive
- Using a combination of `width: 100%` and `max-width` ensures the card is fluid but does not become too large on wide screens.
```css
main {
  width: 100%;
  max-width: 46rem;
  /* ... */
}
```
- I learned how to use `object-fit` and `object-position`.
- `object-fit: cover` makes the image fill its container while keeping its aspect ratio.
- `object-position: center` centers the image within its container.
```css
.image {
  /* ... */
  object-fit: cover;
  object-position: center;
}
```

- Using the `::before` pseudo-element to create custom bullet and number points. This gives more control over the layout. This technique requires using `position: relative` on the parent list item and `position: absolute` on the pseudo-element for precise placement.
```css
.instructions_container__list__item::before {
  position: absolute;
  left: 0.5rem;
  top: 0;
  content: counter(instructions-counter) ".";
  /* ... */
}
```

- Using pseudo-classes like `:not()`, `:first-child`, and `:last-child` to style specific list items without adding extra classes or IDs.

- Aligning items in a table-like layout using the `flex: 1 0 0` shorthand. This shorthand sets `flex-grow`, `flex-shrink`, and `flex-basis`.
```css
.nutrition_container__list__term,
.nutrition_container__list__def {
  flex: 1 0 0;
}
```
### Continued development

In the future, I would like to focus more on accessibility from the start and perhaps explore implementing a light/dark mode theme switcher to further practice using CSS variables and media queries.

### Useful resources

- [The <b> element](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/b) - This page provided details about the `<b>` HTML tag and its semantic use, helping me distinguish it from `<strong>`.


