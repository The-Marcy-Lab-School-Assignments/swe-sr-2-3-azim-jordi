# Technical Writing Assignment

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/fullstack-curriculum/how-tos/working-with-assignments#how-to-work-on-assignments).

## Prompt 1

What are the main differences between Flexbox and Grid layouts? Describe scenarios where each layout system would be more suitable.

### Response 1

## Prompt 2

What is the difference between `justify-content` and `align-items` in Flexbox? How does each property control the positioning of flex items within the container?

### Response 2

The `justify-content` and `align-items` properties in Flexbox control the alignment of flex items but operate on different axes. `justify-content` aligns items along the main axis, while `align-items` aligns items along the cross axis. The orientation of these axes depends on the `flex-direction` property, which defaults to `row` (main axis: horizontal, cross axis: vertical).

For example, with `flex-direction: row`, `justify-content: center` centers items horizontally, whereas `align-items: center` aligns them vertically. When `flex-direction: column`, the axes swap, and `justify-content: center` centers items vertically, while `align-items: center` aligns them horizontally.

Beyond `center`, these properties support values like `flex-start`, `flex-end`, `space-between`, and `space-around`, offering flexibility in arranging items depending on design needs.

## Prompt 3

Describe the difference between `grid-template-areas` and `grid-template-columns`/`grid-template-rows`. When might you prefer one approach over the other?

### Response 3

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
