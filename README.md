# Frontend Mentor - Product preview card component solution

This is a solution to the [Product preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/product-preview-card-component-GO7UmttRfa). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

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
- [Author](#author)




## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover and focus states for interactive elements

### Screenshot

- - Desktop 
https://prnt.sc/hZUTG-Wc7Egt

- - Mobile 
https://prnt.sc/45pgQTKfHIY0



### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox



### What I learned


In this project I've improved my knowledge utilizing media for responsive effect. I've created a Desktop-first and then, using Media, I've adapted to the mobile version. In this example, I've created a media with a property "max-width: 645px", it means that an user using a device with a width screen size lower than 645px will have an adapted version of the content, in this case the image will change. However, the font size will change and the manner of the content display too.   

``` css
@media (max-width: 645px) {

    #responsive-image{
        content: url("../images/image-product-mobile.jpg");
        width: 320px;
        
    }
}

In desktop, the css of the main is applying Flexbox but with a specific change:

```css 
main {
    display: flex;
    width: 600px;
    border-radius: 20px;
    flex-direction: row;
    
}

The flex direction is row, so the elements will be displayed in a row each one.

In mobile, there's a change of the Display flex:

```css
 main{
        display: flex;
        flex-direction: column; 
        place-items: center;
        width: 250px;        
    }

In this case the flex direction is in columns, so the elements won't be displayed forming a line each one. They will be displayed in columns, this is the responsive effect.

Another important knowledge is the use of "border-radius" in css. In this context, if you want to select an specific direction of the border radius, for example if you want a border radius just on the top-right or on the top-left, the first thing you need is to add a border radius in all the elements, and then you remove each side you don't want the border radius: 

First, adding the border-radius in all the image element 

```css 
main .section1 .perfume-desktop {
    /* width: 300px;
    height: 465px; */
    border-radius: 20px;
}

After that, if You want the border radius in some specific part of the container, you have just to remove the sides you don't want:

```html
main .section1 .perfume-desktop {
    /* width: 300px;
    height: 465px; */
    
    border-radius: 20px; /* Apply a border radius to all corners */
    
    
    border-top-right-radius: 0; /* Reset the border radius for the top right corner */
    border-bottom-right-radius: 0; /* Reset the border radius for the bottom right corner */
}

The next concept is a specific issue I've had to treat while doing the responsive: When you select the "display: flex / flex:direction: column" in the parent element, the children elements, consequently will break down and form a vertical line, although for pattern there's an specific space between all the elements, a gap. So each element of the column will get a space among each one. 

There's a specific command to treat this issue: 

```css
    main .section2{
        /* display: flex;
        justify-content: center;
        width: 320px;
        height: 360px; */
        flex: 1; /* used to make the content grow to fill the available space*/
        margin-top: -10px;  /* Adjust this value to remove the desired gap */   
    }

Basically with these two commands I've got to fix that issue. The more you add in margin padding, the more the content of section2 starts to cover the image of the perfume. Consequently, the gap disappears. 
[https://prnt.sc/hYQ4XHhW_Gvk]


Another important knowledge is to centerline an element:

```css
body {
    /* display: flex;
    justify-content: center;
    align-items: center; */
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    /* background-color:#F2E9E4; */
   
}



The last but not the least, I've got another small issue to fix. Basically this was my HTML of the section1.
In this context, I had a second image to replace this one, but I only could change this image accordingly to the max-width in the media. When this width limit is exceeded, another image specifically to mobiles/small screens appear. 


```html
```
<section class="section1">
  <img class="perfume-desktop" src="./src/images/image-product-desktop.jpg" alt="Perfume Photo" id="responsive-image">

</section>

To complete this task of replacing images accordingly to the width, I've put the following CSS command in my media: 

```css 

  #responsive-image{
        content: url("../images/image-product-mobile.jpg");
        width: 320px;
        
}

With this command the images will be changing among mobile and desktop.




### Continued development


I'm satisfied with this final result. I'll keep focusing in responsive layouts, so I want to learn grid layout and improve my knowledge in Flexbox. As I'm a beginner yet, I'll keep studying more about HTML and CSS, furthermore  I want to apply some projects using Javascript. However, my focus now is to dive into the world of WEB development which is my passion. 


### Useful resources

- [ChatGPT] (https://chat.openai.com/share/420b41c3-5858-499e-80b0-00401590a275) - This specific use of ChatGPT helped me to fix the issues of the gap into the columns, the desktop/mobile images and the border-radius.

## Author

- Website - [Paulo Roberto Xavier da Silva](https://p4ulox4vier.github.io/responsive_training-perfume-project/)
- Frontend Mentor - [@P4ULOX4VIER](https://www.frontendmentor.io/profile/P4ULOX4VIER)
- Instagram - [@oxavierpaulo](https://www.instagram.com/oxavierpaulo/)
- GitHub - [@P4ULOX4VIER] (https://github.com/P4ULOX4VIER)
- Linkedin - [@Paulo Roberto Xavier da Silva] (https://www.linkedin.com/in/paulo-roberto-xavier-da-silva-15bb6924a/)
