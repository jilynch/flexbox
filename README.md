# FlexBox

The Odin Prohect FlexBox.

1. [Introduction to Flexbox](#introduction-to-flexbox)
2. [Growing and Shrinking](#growing-and-shrinking)
3. [Axes](#axes)
4. [Alignment](#alignment)

## Introduction to Flexbox

When we describe flexbox as being one dimensional we are describing the fact that flexbox deals with layout in one dimension at a time — either as a row or as a column.

### Flex conteiner and Flex items

A flex container is any element that has `display: flex` or `display: inline-flex` on it. A flex item is any element that lives directly inside of a flex container. As soon as we do this the direct children of that container become **flex items**.

![flex-conteiner-item](https://cdn.statically.io/gh/TheOdinProject/curriculum/495704c6eb6bf33bc927534f231533a82b27b2ac/html_css/v2/foundations/flexbox/imgs/03.png)

Flex container default values:

-   Items display in a row (the `flex-direction` property's default is `row`).
-   The items start from the start edge of the main axis.
-   The items do not stretch on the main dimension, but can shrink.
-   The items will stretch to fill the size of the cross axis.
-   The `flex-basis` property is set to `auto`.
-   The `flex-wrap` property is set to `nowrap`.

Any element can be both a flex container _and_ a flex item, put `display: flex` on a flex item, and then use flexbox to arrange its children.

![flex-item-container](https://cdn.statically.io/gh/TheOdinProject/curriculum/495704c6eb6bf33bc927534f231533a82b27b2ac/html_css/v2/foundations/flexbox/imgs/04.png)

### The flex-flow shorthand

You can combine the two properties `flex-direction` and `flex-wrap` into the `flex-flow` shorthand. The first value specified is flex-direction and the second value is flex-wrap.

-   `flex-flow: row wrap;`

### Multi-line flex containers with flex-wrap

To cause wrapping behavior add the property `flex-wrap` with a value of `wrap`.

## Growing and Shrinking

To have more control over flex items we can target them directly. We do this by way of three properties:

-   `flex-grow`: How much of the positive free space does this item get?
-   `flex-shrink`: How much negative free space can be removed from this item?
-   `flex-basis`: What is the size of the item before growing and shrinking happens?

You will very rarely see the `flex-grow`, `flex-shrink`, and `flex-basis` properties used individually; instead they are combined into the `flex` shorthand.

-   `flex: 1 1 auto;`

### Positive and negative free space

When a flex container has positive free space, it has more space than is required to display the flex items inside the container.

![positive-free-space](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Controlling_Ratios_of_Flex_Items_Along_the_Main_Ax/basics7.png)

We have negative free space when the natural size of the items adds up to larger than the available space in the flex container

![negative-free-space](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Controlling_Ratios_of_Flex_Items_Along_the_Main_Ax/ratios1.png)

### The `flax-basis` property

The `flex-basis` property specifies the initial size of the flex item before any space distribution happens. The initial value for this property is `auto`. If `flex-basis` is set to `auto` then to work out the initial size of the item the browser first checks if the main size of the item has an absolute size set.
If your item is instead auto-sized, then `auto` resolves to the size of its content. At this point your knowledge of `min-` and `max-content` sizing becomes useful, as flexbox will take the `max-content` size of the item as the `flex-basis`.

## Axes

When working with flexbox you need to think in terms of two axes — the main axis and the cross axis. The main axis is defined by the `flex-direction` property, and the cross axis runs perpendicular to it.

Another vital area of understanding is how flexbox makes no assumption about the writing mode of the document.
If the `flex-direction` is `row` and I am working in English, then the start edge of the main axis will be on the left, the end edge on the right.

![main-axis-flex-direction-row-englis](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox/basics5.png)

If I were to work in Arabic, then the start edge of my main axis would be on the right and the end edge on the left.

![main-axis-flex-direction-row-arabic](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox/basics6.png)

### The main axis

The main axis is defined by `flex-direction`, which has four possible values:

-   row
-   row-reverse
-   column
-   column-reverse

Should you choose `row` or `row-reverse`, your main axis will run along the row in the **inline direction**.

![main-axes-flex-direction-row](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox/basics1.png)

Choose `column` or `column-reverse` and your main axis will run from the top of the page to the bottom — in the **block direction**.

![main-axis-flex-direction-row](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox/basics2.png)

### The corss axis

The cross axis runs perpendicular to the main axis, therefore if your `flex-direction` (main axis) is set to `row` or `row-reverse` the cross axis runs down the columns.

![cors-axis-flex-direction-row](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox/basics3.png)

If your main axis is `column` or `column-reverse` then the cross axis runs along the rows.

![cors-axis-flex-direction-column](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox/basics4.png)

## Alignment

A key feature of flexbox is the ability to align and justify items on the main- and cross-axes, and to distribute space between flex items. Note that these properties are to be set on the flex container, not on the items themselves.

### `align-items`

The `align-items` property will align the items on the cross axis.

-   `align-items:`
    -   `stretch`
    -   `flex-start`
    -   `flex-end`
    -   `center`

### `justify-content`

The `justify-content` property is used to align the items on the main axis, the direction in which `flex-direction` has set the flow.

-   `justify-content`
    -   `flex-start`
    -   `flex-end`
    -   `center`
    -   `space-around`
    -   `space-between`
    -   `space-evenly`
