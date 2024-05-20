# CSS Cheat Sheet


## Pseudo-elements

A CSS **pseudo-element** is a keyword added to a selector that lets you style a specific **part** of the selected element(s).

Double colons (`::`) are used for pseudo-elements.

 **Syntax** 

```css
selector::pseudo-element {
    property: value;
  }
```

### List of pseudo-elements

* `::after`

* `::backdrop`

* `::before`

* `::cue`

* `::cue-region`

* `::first-letter`

* `::first-line`

* `::file-selector-button`

* `::grammar-error Experimental`

* `::marker`

* `::part()`

* `::placeholder`

* `::selection`

* `::slotted()`

* `::spelling-error Experimental`

* `::target-text Experimental`



### Examples
<docs-code-multifile preview path="src/content/examples/css/pseudo-elements/pseudo-elements.component.ts">
<docs-code language="css" header="syntax" visibleRegion="pseudo-element-syntax"  path="src/content/examples/css/pseudo-elements/pseudo-elements.component.css"/>
<docs-code language="css" header="first-line" visibleRegion="pseudo-element-first-line"  path="src/content/examples/css/pseudo-elements/pseudo-elements.component.css"/>
<docs-code language="css" header="after" visibleRegion="after"  path="src/content/examples/css/pseudo-elements/pseudo-elements.component.css"/>
</docs-code-multifile>


NOTE: CSS introduced the `::before`, `::after`, `::first-line`, and `::first-letter` notation (with two colons) to distinguish _pseudo-classes_ from _pseudo-elements_. For backward compatibility, browsers also accept the single colon syntax.


## Pseudo-classes

A CSS **pseudo-class** is a keyword added to a selector that specifies a special **state** of the selected element(s).

* A **pseudo-class** consists of a colon (`:`) followed by the pseudo-class _name_ (e.g., `:hover`). 
* A **functional pseudo-class** also contains a pair of parentheses to define the arguments (e.g., `:dir()`). 
* The `element` that a pseudo-class is attached to is defined as an `anchor element` (e.g., `button` in case `button:hover`).


**Syntax**

```css
selector:pseudo-class {
  property: value;
}
```


### Tree-structural pseudo-classes

These pseudo-classes relate to the **location** of an element **within the document tree**.

* `:root`
Represents an element that is the root of the document. In HTML this is usually the <html> element.

* `:empty`
Represents an element with no children other than white-space characters.

* `:nth-child`
Uses An+B notation to select elements from a list of sibling elements.

* `:nth-last-child`
Uses An+B notation to select elements from a list of sibling elements, counting backwards from the end of the list.

* `:first-child`
Matches an element that is the first of its siblings.

* `:last-child`
Matches an element that is the last of its siblings.

* `:only-child`
Matches an element that has no siblings. For example, a list item with no other list items in that list.

* `:nth-of-type`
Uses An+B notation to select elements from a list of sibling elements that match a certain type from a list of sibling elements.

* `:nth-last-of-type`
Uses An+B notation to select elements from a list of sibling elements that match a certain type from a list of sibling elements counting backwards from the end of the list.

* `:first-of-type`
Matches an element that is the first of its siblings, and also matches a certain type selector.

* `:last-of-type`
Matches an element that is the last of its siblings, and also matches a certain type selector.

* `:only-of-type`
Matches an element that has no siblings of the chosen type selector.


### Functional pseudo-classes

These pseudo-classes accept a **selector list** or forgiving selector list as a parameter.

* `:is()`
The matches-any pseudo-class matches any element that matches any of the selectors in the list provided. The list is forgiving.

* `:not()`
The negation, or matches-none, pseudo-class represents any element that is not represented by its argument.

* `:where()`
The specificity-adjustment pseudo-class matches any element that matches any of the selectors in the list provided without adding any specificity weight. The list is forgiving.

* `:has()`
The relational pseudo-class represents an element if any of the relative selectors match when anchored against the attached element.

### User action pseudo-classes

These pseudo-classes require some **interaction by the user** in order for them to apply, such as holding a mouse pointer over an element.

* `:hover`
Matches when a user designates an item with a pointing device, such as holding the mouse pointer over the item.

* `:active`
Matches when an item is being activated by the user. For example, when the item is clicked on.

* `:focus`
Matches when an element has focus.

* `:focus-visible`
Matches when an element has focus and the user agent identifies that the element should be visibly focused.

* `:focus-within`
Matches an element to which :focus applies, plus any element that has a descendant to which :focus applies.

### Linguistic pseudo-classes

These pseudo-classes reflect the document language and enable the **selection of elements based on language or script direction**.

* `:dir()` The directionality pseudo-class selects an element based on its directionality as determined by the document language.

* `:lang()` Select an element based on its content language.


### Examples
<docs-code-multifile preview path="src/content/examples/css/pseudo-classes/pseudo-classes.component.ts">
<docs-code language="css" header="syntax" visibleRegion="syntax"  path="src/content/examples/css/pseudo-classes/pseudo-classes.component.css"/>
<docs-code language="css" header="hover" visibleRegion="hover"  path="src/content/examples/css/pseudo-classes/pseudo-classes.component.css"/>
</docs-code-multifile>




## Animations

CSS animations make it possible to **animate transitions from one CSS style configuration to another**.
Animations consist of two components, a style describing the CSS animation and a set of keyframes that indicate the start and end states of the animation's style, as well as possible intermediate waypoints.

### Configuring an animation

To create a CSS animation sequence, you style the element you want to animate with the animation property or its sub-properties. This lets you configure the timing, duration, and other details of how the animation sequence should progress. This does not configure the actual appearance of the animation, which is done using the [`@keyframes`](#defining-animation-sequence-using-keyframes) .

### The sub-properties of the animation property are:

`animation-composition`
Specifies the composite operation to use when multiple animations affect the same property simultaneously. This property is not part of the animation shorthand property.

[`animation-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay)
Specifies the delay between an element loading and the start of an animation sequence and whether the animation should start immediately from its beginning or partway through the animation.

`animation-direction`
Specifies whether an animation's first iteration should be forward or backward and whether subsequent iterations should alternate direction on each run through the sequence or reset to the start point and repeat.

`animation-duration`
Specifies the **length of time in which an animation completes one cycle**.

`animation-fill-mode`
Specifies how an animation applies styles to its target before and after it runs.

`animation-iteration-count`
Specifies the number of times an animation should repeat.

`animation-name`
Specifies the name of the @keyframes at-rule describing an animation's keyframes.

`animation-play-state`
Specifies whether to pause or play an animation sequence.

`animation-timeline Experimental`
Specifies the timeline that is used to control the progress of a CSS animation.

`animation-timing-function`
Specifies **how an animation transitions through keyframes** by establishing acceleration curves.

### Defining animation sequence using keyframes

After you've configured the animation's timing, you need to define the appearance of the animation. This is done by establishing one or more keyframes using the `@keyframes` at-rule.
Each keyframe describes how the animated element should render at a given time during the animation sequence.

Since the timing of the animation is defined in the CSS style that configures the animation, keyframes use a `<percentage>` to indicate the time during the animation sequence at which they take place.

- `0% (/from)` indicates the first moment of the animation sequence
- `100% (/to)` indicates the final state of the animation.

If from/0% or to/100% is not specified, the browser starts or finishes the animation using the computed values of all attributes.

You can optionally include additional keyframes that describe intermediate steps between the start and end of the animation.

### Using the animation shorthand

The animation shorthand is useful for saving space.
As an example,

```css
p {
  animation-duration: 3s;
  animation-name: slidein;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}
```

could be replaced by using the animation shorthand

```css
animation: 3s infinite alternate slidein;
```

## Transitions

CSS transitions provide a way to **control animation speed when changing CSS properties**.
Instead of having property changes take effect immediately,
you can cause the changes in a property to take place over a period of time.

For example, if you change the color of an element from white to black, usually the change is instantaneous.
With CSS transitions enabled, changes occur at time intervals that follow an acceleration curve, all of which can be customized.

Animations that involve transitioning between two states are often called implicit transitions as the states in between the start and final states are implicitly defined by the browser.

### Defining transitions

CSS Transitions are controlled using the shorthand `transition` property.
This is the best way to configure transitions, as it makes it easier to avoid out of sync parameters, which can be very frustrating to have to spend lots of time debugging in CSS.

You can control the individual components of the transition with the following sub-properties:

`transition-property`
Specifies the name or names of the CSS properties to which transitions should be applied. Only properties listed here are animated during transitions; changes to all other properties occur instantaneously as usual.

`transition-duration`
Specifies the duration over which transitions should occur. You can specify a single duration that applies to all properties during the transition, or multiple values to allow each property to transition over a different period of time.

`transition-timing-function`
Specifies a function to define how intermediate values for properties are computed. Easing functions determine how intermediate values of the transition are calculated. Most easing functions can be specified by providing the graph of the corresponding function, as defined by four points defining a cubic bezier. You can also choose easing from Easing functions cheat sheet.

`transition-delay`
Defines how long to wait between the time a property is changed and the transition actually begins.

#### Basic example

This example performs a four-second font size transition with a two-second delay between the time the user mouses over the element and the beginning of the animation effect:

```css
#delay {
  font-size: 14px;
  transition-property: font-size;
  transition-duration: 4s;
  transition-delay: 2s;
}

#delay:hover {
  font-size: 36px;
}
```

#### Multiple animated properties example

```css
.box {
  border-style: solid;
  border-width: 1px;
  display: block;
  width: 100px;
  height: 100px;
  background-color: #0000ff;
  transition: width 2s, height 2s, background-color 2s, rotate 2s;
}

.box:hover {
  background-color: #ffcccc;
  width: 200px;
  height: 200px;
  rotate: 180deg;
}
```

#### When property value lists are of different lengths

If any property's list of values is shorter than the others, its values are repeated to make them match. For example:

```css
div {
  transition-property: opacity, left, top, height;
  transition-duration: 3s, 5s;
}
```

This is treated as if it were:

```css
div {
  transition-property: opacity, left, top, height;
  transition-duration: 3s, 5s, 3s, 5s;
}
```

Similarly, if any property's value list is longer than that for transition-property, it's truncated, so if you have the following CSS:

```css
div {
  transition-property: opacity, left;
  transition-duration: 3s, 5s, 2s, 1s;
}
```

This gets interpreted as:

```css
div {
  transition-property: opacity, left;
  transition-duration: 3s, 5s;
}
```





<docs-callout schedule  title="Comming Soon ;) ">
  <docs-pill-row>
    <docs-pill href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_containment/Container_size_and_style_queries" title="Style Queries"/>
    <docs-pill href="https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties"  title="Custom properties"/>
    <docs-pill href="https://developer.mozilla.org/en-US/docs/Web/CSS/:has" title=" :has() CSS pseudo-class "/>

  </docs-pill-row>
</docs-callout>