# Frontend Mentor - Fylo data storage component solution

This is a solution to the [Fylo data storage component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/fylo-data-storage-component-1dZPRbV5n). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Thinking process](#thinking-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size

### Screenshot

![](./screenshots/desktop%20view.png)

### Links

- Solution URL: [Solution](https://github.com/hachem89/Frontend-Mentor---Fylo-data-storage-component-solution)
- Live Site URL: [Live site](https://hachem89.github.io/Frontend-Mentor---Fylo-data-storage-component-solution/)

## My process

### Thinking process

- So when i first saw the project i realised that in the desktop design there is like a dialogue bubble that contains how much of the storage left. But in the mobile design, the storage left is in a classique box so i thought how can i design this dialogue bubble?. So i used pseudo-element "::after" for the p.storage-left, insert content that is empty, set the height and width of the pseudo-element to 30px each, osition the pseudo-element absolutely to the right of the parent element, place the pseudo-element at the bottom with an offset of -30px, and ==the trick is to apply a linear gradient background, starting with dark blue (0-50%) and transitioning to white (50-100%) diagonally at a 45-degree angle.==
  But when i do this it will appear in mobile too so that's why i started with the mobile design and i used media query to style the dialogue bubble for the desktop like this

```css
/* for mobile */
p.storage-left {
  align-self: center;
  padding: 0.5rem 1.5rem;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.7rem;
  background-color: white;
  border-radius: 10px 10px 0 10px;
  color: var(--Grayish-Blue);
  font-weight: var(--fw-700);
  position: absolute;
  bottom: -50px;
}

/* for desktop */
@media (min-width: 700px) {
  p.storage-left {
    top: -60px;
    bottom: auto;
    right: 50px;
  }

  p.storage-left::after {
    content: "";
    height: 30px;
    width: 30px;
    background: linear-gradient(45deg, var(--Dark-Blue) 0 50%, white 50% 100%);
    position: absolute;
    right: 0;
    bottom: -30px;
  }
}
```

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow

### What I learned

- I learned that little trick that i talked about in my [thinking process](#thinking-process)

- I learned that the ==background-size== CSS property sets the size of the element's background image. The image can be left to its natural size, stretched, or constrained to fit the available space and it can have multiple values.

```css
/* Keyword values */
background-size: cover;
background-size: contain;

/* One-value syntax */
/* the width of the image (height becomes 'auto') */
background-size: 50%;
background-size: 3.2em;
background-size: 12px;
background-size: auto;

/* Two-value syntax */
/* first value: width of the image, second value: height */
background-size: 50% auto;
background-size: 3em 25%;
background-size: auto 6px;
background-size: auto auto;

/* Multiple backgrounds */
background-size: auto, auto; /* Not to be confused with `auto auto` */
background-size: 50%, 25%, 25%;
background-size: 6px, auto, contain;

/* Global values */
background-size: inherit;
background-size: initial;
background-size: revert;
background-size: revert-layer;
background-size: unset;
```

- I learned about ==font-variant-numeric== to style the numbers in a text like this:

```html
<p class="my-text">The year 1776 is an important date in history.</p>
```

```css
.my-text {
  font-variant-numeric: oldstyle-nums;
}
/*
The oldstyle-nums value is a part of this property and is used to render numbers using an older, more traditional style. This can create a visually appealing effect, especially in designs that aim for a vintage or classic look.
*/
```

- I learned how to make a progress bar but i don't think i did it in the best way (i may make it harder). So please if you know a better way let me know by contributing 😀

### Continued development

I want to practice more about ==responsive design== because I want to get better at making websites that look good on all kinds of devices, like phones, tablets, and computers. I think it's important to make sure that everyone can easily use and see the things I create online, no matter what device they're using. So, I'm excited to learn more about how to design and build websites that work well and look nice everywhere.

### Useful resources

- [Complete guide to CSS grid](https://css-tricks.com/snippets/css/complete-guide-grid/)

## Author

- Frontend Mentor - [@hachem89](https://www.frontendmentor.io/profile/hachem89)
