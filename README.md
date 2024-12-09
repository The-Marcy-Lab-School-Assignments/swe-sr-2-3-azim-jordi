# Technical Writing Assignment

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/fullstack-curriculum/how-tos/working-with-assignments#how-to-work-on-assignments).

## Prompt 1

What are the main differences between Flexbox and Grid layouts? Describe scenarios where each layout system would be more suitable.

### Response 1

`Flexbox` is designed for one dimensional layout, either a row or a column. `Grid` is designed for two-dimensional layout, rows and columns at the same time. There are some key differences between both depending on the complexity of the layout. `Flexbox` is mainly used for simpler, and linear layouts and they allows more flexibility. You can use it for designing navigation menus or aligning content horizontally/vertically. For example:

```html
<nav class="navbar">
  <div class="logo">MySite</div>
  <ul class="nav-links">
    <li><a href="#home">Home</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>
```

```css
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #333;
  color: white;
  padding: 10px 20px;
}
```

Navigation bar is easily styled with flex/flex-box display property. Here is an example using `Grid` layout:

```css
.navbar {
  display: grid;
  grid-template-columns: 1fr auto auto;
  align-items: center;
  background-color: #333;
  color: white;
  padding: 10px 20px;
}
```

With `Grid`, you can define a structured layout that divides the navigation bar into three sections: a flexible space for the logo, a section for the links, and another for additional elements like a call-to-action button. This makes `Grid` more suitable for layouts requiring precise positioning of items in two dimensions.

## Prompt 2

What is the difference between `justify-content` and `align-items` in Flexbox? How does each property control the positioning of flex items within the container?

### Response 2

The `justify-content` and `align-items` properties in Flexbox control the alignment of flex items but operate on different axes. `justify-content` aligns items along the main axis, while `align-items` aligns items along the cross axis. The orientation of these axes depends on the `flex-direction` property, which defaults to `row` (main axis: horizontal, cross axis: vertical).

For example, with `flex-direction: row`, `justify-content: center` centers items horizontally, whereas `align-items: center` aligns them vertically. When `flex-direction: column`, the axes swap, and `justify-content: center` centers items vertically, while `align-items: center` aligns them horizontally.

Beyond `center`, these properties support values like `flex-start`, `flex-end`, `space-between`, and `space-around`, offering flexibility in arranging items depending on design needs.

## Prompt 3

Describe the difference between `grid-template-areas` and `grid-template-columns`/`grid-template-rows`. When might you prefer one approach over the other?

### Response 3

The main difference is how they define the structure of the grid layout:

1. `grid-template-areas`:

- Allows you to define a grid using named areas with text-based template that visually maps out the arrangement of the elements.
- It's is more descriptive and visually intuitive, making it easier to understand and manage complex layouts.

```css
.grid-container {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar content"
    "footer footer";
  grid-template-columns: 1fr 3fr;
  grid-template-rows: auto 1fr auto;
}
.header {
  grid-area: header;
}
.sidebar {
  grid-area: sidebar;
}
.content {
  grid-area: content;
}
.footer {
  grid-area: footer;
}
```

- `the grid-template-areas` visually maps the layout with clear labels like `header`, `sidebar`, `content`, and `footer`

2. `grid-template-columns`/`grid-template-rows`:

- They define the size of the columns and rows explicitly using measurements without naming and mapping areas.
- This approach provides precise control over row and column sizes without requiring named areas.

```css
.grid-container {
  display: grid;
  grid-template-columns: 1fr 3fr;
  grid-template-rows: auto 1fr auto;
}
.item1 {
  grid-column: 1 / 3;
  grid-row: 1;
}
.item2 {
  grid-column: 1;
  grid-row: 2;
}
.item3 {
  grid-column: 2;
  grid-row: 2;
}
.item4 {
  grid-column: 1 / 3;
  grid-row: 3;
}
```

Here, you position items by specifying start and end lines for rows and columns. You would use one method over the other depending on the complexity of your project, and the level of control or clarity you need.

## Prompt 4

Explain the `min-width` and `max-width` keywords in media queries. How do they help create responsive breakpoints for different screen sizes?

### Response 4

In CSS media queries are used to accommodate web content across different screen sizes with the objective of delivering the most optimal user experience.
Two key properties for making a responsive website while using media queries are the `min-width` and `max-width` properties. Both properties help to set responsive breakpoints for different screen sizes.

To understand the relation between media queries and the min and max width properties better let's look at this CSS code snippet for example:

```css
@media (min-width: 576px) {
  .grid-container {
    grid-template-columns: 1fr 1fr;
  }
}
```

In this case the styling inside of the media code block will apply to the `grid-container` class when the minimum width of the viewport is 576px or higher, commonly targeting a small device in landscape orientation.

Conversely, the `max-width` property applies styles up to a specified maximum width:

```css
@media (max-width: 768px) {
  .grid-container {
    grid-template-columns: 1fr 1fr;
  }
}
```

In this example, When using `max-width`, the styling for the `grid-container` class applies only when the width of the viewport is 768px or smaller, targeting devices with lower resolutions.

By combining the `min-width` and `max-width` properties with media queries we can define specific ranges for our breakpoints to efficiently rearrange web content to fit the page, ensuring that users from different devices have the best experience.

## Prompt 5

Imagine you are teaching a brief lesson on **mobile first design**. Your lesson should include the following information:

- An explanation of mobile first design and a few of the benefits of this approach
- A CSS code example demonstrating how to use media queries to adjust the layout of a container from mobile to desktop with either Flexbox or Grid (choose one).
- An explanation of the code example.

### Response 5

### Mobile First Design

The mobile first design approach to web design, as the name states focuses on designing the mobile versions of a webpage first before proceeding to develop tablet, desktop, and other versions.
At a first glance, it can be easy to underestimate the value of this approach but there are many benefits that come from following this approach when designing a website.

- **Progressive Enhancement**
  - In the context of web design, progressive enhancement is the idea that by developing a website on the smallest screen resolution, developers are forced to prioritize the most essential features, which makes building different versions of the webpage easier as the user experience aspect of the site is concrete from the beginning.
- **Mobile first approach is a content-first approach**
  - Given the narrow resolution of mobile devices, developers are required to prioritize the most important content of the webpage, which often are critical pieces of information. This ensures that the most important pieces of the webpage are not overlooked.
- **Visual Hierarchy**
  - Mobile-first design helps developers think about how the website content is organized due to the smaller space available for content. This ensures that the hierarchy of our content is clear and is appropriately prioritized.

#### Take a look at the example below:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Mobile-First Example</title>
    <style>
      /* Base styles for mobile (default) */
      .container {
        display: flex;
        flex-direction: column;
        gap: 10px;
        padding: 10px;
      }
      .box {
        background-color: #4caf50;
        color: white;
        text-align: center;
        padding: 20px;
        border-radius: 5px;
      }
      /* Styles for larger screens */
      @media (min-width: 768px) {
        .container {
          flex-direction: row;
          justify-content: space-between;
        }
      }
    </style>
  </head>
  <body>
    <div class="container">
      <div class="box">Box 1</div>
      <div class="box">Box 2</div>
      <div class="box">Box 3</div>
    </div>
  </body>
</html>
```

#### 1. Default Mobile Styles:

- The `.container` uses `flex-direction: column`, stacking the child `.box` elements vertically.
- A `gap` property is added for spacing between the boxes.
- This ensures a simple and readable layout optimized for smaller screens.

#### 2. Media Query for Larger Screens:

- The `@media (min-width: 768px)` rule applies styles for devices with a screen width of 768px or larger (e.g., tablets and desktops).
- The `.container` switches to `flex-direction: row`, aligning the boxes horizontally.
- `justify-content: space-between` ensures even spacing between the boxes.
  In our code, default styles are designed for smaller screens, and adjustments are progressively added for larger screens using a media query. This approach ensures that the design is efficient and functional on mobile devices by default. Mobile-first design focuses on prioritizing the needs and constraints of smaller screens, laying a solid foundation before scaling up for larger devices. This approach simplifies the process of adding enhancements for bigger screens. By leveraging media queries, you can build responsive and adaptable layouts that provide a seamless experience across all screen sizes.
