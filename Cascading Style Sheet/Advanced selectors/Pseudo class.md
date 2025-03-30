

A [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) **_pseudo-class_** is a keyword added to a selector that lets you style a specific state of the selected element(s). For example, the pseudo-class [`:hover`](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover) can be used to select a button when a user's pointer hovers over the button and this selected button can then be styled.



```css

/* Any button over which the user's pointer is hovering */
button:hover {
  color: blue;
}
```

A pseudo-class consists of a colon (`:`) followed by the pseudo-class name (e.g., `:hover`). A functional pseudo-class also contains a pair of parentheses to define the arguments (e.g., `:dir()`). The element that a pseudo-class is attached to is defined as an _anchor element_ (e.g., `button` in case `button:hover`).

Pseudo-classes let you apply a style to an element not only in relation to the content of the document tree, but also in relation to external factors like the history of the navigator ([`:visited`](https://developer.mozilla.org/en-US/docs/Web/CSS/:visited), for example), the status of its content (like [`:checked`](https://developer.mozilla.org/en-US/docs/Web/CSS/:checked) on certain form elements), or the position of the mouse (like [`:hover`](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover), which lets you know if the mouse is over an element or not).

**Note:** In contrast to pseudo-classes, [pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) can be used to style a _specific part_ of an element.

## [Elemental pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#elemental_pseudo-classes)

These pseudo-classes relate to the core identity of elements.

[`:defined`](https://developer.mozilla.org/en-US/docs/Web/CSS/:defined)

Matches any element that is defined.

## [Element display state pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#element_display_state_pseudo-classes)

These pseudo-classes enable the selection of elements based on their display states.

[`:open`](https://developer.mozilla.org/en-US/docs/Web/CSS/:open)

Matches an element that can either be open or closed that is currently open.

[`:popover-open`](https://developer.mozilla.org/en-US/docs/Web/CSS/:popover-open)

Matches a popover element that is currently in the showing state.

[`:modal`](https://developer.mozilla.org/en-US/docs/Web/CSS/:modal)

Matches an element that is in a state in which it excludes all interaction with elements outside it until the interaction has been dismissed.

[`:fullscreen`](https://developer.mozilla.org/en-US/docs/Web/CSS/:fullscreen)

Matches an element that is currently in fullscreen mode.

[`:picture-in-picture`](https://developer.mozilla.org/en-US/docs/Web/CSS/:picture-in-picture)

Matches an element that is currently in picture-in-picture mode.

## [Input pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#input_pseudo-classes)

These pseudo-classes relate to form elements, and enable selecting elements based on HTML attributes and the state that the field is in before and after interaction.

[`:enabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:enabled)

Represents a user interface element that is in an enabled state.

[`:disabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:disabled)

Represents a user interface element that is in a disabled state.

[`:read-only`](https://developer.mozilla.org/en-US/docs/Web/CSS/:read-only)

Represents any element that cannot be changed by the user.

[`:read-write`](https://developer.mozilla.org/en-US/docs/Web/CSS/:read-write)

Represents any element that is user-editable.

[`:placeholder-shown`](https://developer.mozilla.org/en-US/docs/Web/CSS/:placeholder-shown)

Matches an input element that is displaying placeholder text. For example, it will match the `placeholder` attribute in the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) and [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) elements.

[`:autofill`](https://developer.mozilla.org/en-US/docs/Web/CSS/:autofill)

Matches when an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) has been autofilled by the browser.

[`:default`](https://developer.mozilla.org/en-US/docs/Web/CSS/:default)

Matches one or more UI elements that are the default among a set of elements.

[`:checked`](https://developer.mozilla.org/en-US/docs/Web/CSS/:checked)

Matches when elements such as checkboxes and radio buttons are toggled on.

[`:indeterminate`](https://developer.mozilla.org/en-US/docs/Web/CSS/:indeterminate)

Matches UI elements when they are in an indeterminate state.

[`:blank`](https://developer.mozilla.org/en-US/docs/Web/CSS/:blank)

Matches a user-input element which is empty, containing an empty string or other null input.

[`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid)

Matches an element with valid contents. For example, an input element with the type 'email' that contains a validly formed email address or an empty value if the control is not required.

[`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)

Matches an element with invalid contents. For example, an input element with type 'email' with a name entered.

[`:in-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:in-range)

Applies to elements with range limitations. For example, a slider control when the selected value is in the allowed range.

[`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range)

Applies to elements with range limitations. For example, a slider control when the selected value is outside the allowed range.

[`:required`](https://developer.mozilla.org/en-US/docs/Web/CSS/:required)

Matches when a form element is required.

[`:optional`](https://developer.mozilla.org/en-US/docs/Web/CSS/:optional)

Matches when a form element is optional.

[`:user-valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:user-valid)

Represents an element with correct input, but only when the user has interacted with it.

[`:user-invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:user-invalid)

Represents an element with incorrect input, but only when the user has interacted with it.

## [Linguistic pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#linguistic_pseudo-classes)

These pseudo-classes reflect the document language and enable the selection of elements based on language or script direction.

[`:dir()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:dir)

The directionality pseudo-class selects an element based on its directionality as determined by the document language.

[`:lang()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:lang)

Select an element based on its content language.

## [Location pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#location_pseudo-classes)

These pseudo-classes relate to links, and to targeted elements within the current document.

[`:any-link`](https://developer.mozilla.org/en-US/docs/Web/CSS/:any-link)

Matches an element if the element would match either [`:link`](https://developer.mozilla.org/en-US/docs/Web/CSS/:link) or [`:visited`](https://developer.mozilla.org/en-US/docs/Web/CSS/:visited).

[`:link`](https://developer.mozilla.org/en-US/docs/Web/CSS/:link)

Matches links that have not yet been visited.

[`:visited`](https://developer.mozilla.org/en-US/docs/Web/CSS/:visited)

Matches links that have been visited.

[`:local-link`](https://developer.mozilla.org/en-US/docs/Web/CSS/:local-link)

Matches links whose absolute URL is the same as the target URL. For example, anchor links to the same page.

[`:target`](https://developer.mozilla.org/en-US/docs/Web/CSS/:target)

Matches the element which is the target of the document URL.

[`:target-within`](https://developer.mozilla.org/en-US/docs/Web/CSS/:target-within)

Matches elements which are the target of the document URL, but also elements which have a descendant which is the target of the document URL.

[`:scope`](https://developer.mozilla.org/en-US/docs/Web/CSS/:scope)

Represents elements that are a reference point for selectors to match against.

## [Resource state pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#resource_state_pseudo-classes)

These pseudo-classes apply to media that is capable of being in a state where it would be described as playing, such as a video.

[`:playing`](https://developer.mozilla.org/en-US/docs/Web/CSS/:playing)

Represents a playable element that is playing.

[`:paused`](https://developer.mozilla.org/en-US/docs/Web/CSS/:paused)

Represents a playable element that is paused.

[`:seeking`](https://developer.mozilla.org/en-US/docs/Web/CSS/:seeking)

Represents a playable element that is currently seeking a playback position in the media resource.

[`:buffering`](https://developer.mozilla.org/en-US/docs/Web/CSS/:buffering)

Represents a playable element that is playing but is temporarily stalled because it is downloading the media resource.

[`:stalled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:stalled)

Represents a playable element that is playing but is stalled because it cannot download the media resource.

[`:muted`](https://developer.mozilla.org/en-US/docs/Web/CSS/:muted)

Represents a sound-producing element that is muted.

[`:volume-locked`](https://developer.mozilla.org/en-US/docs/Web/CSS/:volume-locked)

Represents a sound-producing element that has its volume level locked by the browser.

## [Time-dimensional pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#time-dimensional_pseudo-classes)

These pseudo-classes apply when viewing something which has timing, such as a [WebVTT](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API) caption track.

[`:current`](https://developer.mozilla.org/en-US/docs/Web/CSS/:current)

Represents the element or ancestor of the element that is being displayed.

[`:past`](https://developer.mozilla.org/en-US/docs/Web/CSS/:past)

Represents an element that occurs entirely before the [`:current`](https://developer.mozilla.org/en-US/docs/Web/CSS/:current) element.

[`:future`](https://developer.mozilla.org/en-US/docs/Web/CSS/:future)

Represents an element that occurs entirely after the [`:current`](https://developer.mozilla.org/en-US/docs/Web/CSS/:current) element.

## [Tree-structural pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#tree-structural_pseudo-classes)

These pseudo-classes relate to the location of an element within the document tree.

[`:root`](https://developer.mozilla.org/en-US/docs/Web/CSS/:root)

Represents an element that is the root of the document. In HTML this is usually the `<html>` element.

[`:empty`](https://developer.mozilla.org/en-US/docs/Web/CSS/:empty)

Represents an element with no children other than white-space characters.

[`:nth-child()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child)

Uses `An+B` notation to select elements from a list of sibling elements.

[`:nth-last-child()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-last-child)

Uses `An+B` notation to select elements from a list of sibling elements, counting backwards from the end of the list.

[`:first-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:first-child)

Matches an element that is the first of its siblings.

[`:last-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:last-child)

Matches an element that is the last of its siblings.

[`:only-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:only-child)

Matches an element that has no siblings. For example, a list item with no other list items in that list.

[`:nth-of-type()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-of-type)

Uses `An+B` notation to select elements from a list of sibling elements that match a certain type from a list of sibling elements.

[`:nth-last-of-type()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-last-of-type)

Uses `An+B` notation to select elements from a list of sibling elements that match a certain type from a list of sibling elements counting backwards from the end of the list.

[`:first-of-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/:first-of-type)

Matches an element that is the first of its siblings, and also matches a certain type selector.

[`:last-of-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/:last-of-type)

Matches an element that is the last of its siblings, and also matches a certain type selector.

[`:only-of-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/:only-of-type)

Matches an element that has no siblings of the chosen type selector.

## [Shadow-structural pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#shadow-structural_pseudo-classes)

These pseudo-classes relate to the shadow DOM.

[`:host`](https://developer.mozilla.org/en-US/docs/Web/CSS/:host)

Matches the shadow tree's shadow host.

[`:host()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:host_function)

Matches an element that matches [`:host`](https://developer.mozilla.org/en-US/docs/Web/CSS/:host) and matches any of the selectors in the list provided.

[`:host-context()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:host-context)

Selects elements outside of the shadow tree in the context of the shadow host.

[`:has-slotted`](https://developer.mozilla.org/en-US/docs/Web/CSS/:has-slotted)

Matches slot elements that have been assigned content.

## [User action pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#user_action_pseudo-classes)

These pseudo-classes require some interaction by the user in order for them to apply, such as holding a mouse pointer over an element.

[`:hover`](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover)

Matches when a user designates an item with a pointing device, such as holding the mouse pointer over the item.

[`:active`](https://developer.mozilla.org/en-US/docs/Web/CSS/:active)

Matches when an item is being activated by the user. For example, when the item is clicked on.

[`:focus`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus)

Matches when an element has focus.

[`:focus-visible`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-visible)

Matches when an element has focus and the user agent identifies that the element should be visibly focused.

[`:focus-within`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-within)

Matches an element to which [`:focus`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus) applies, plus any element that has a descendant to which [`:focus`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus) applies.

## [Functional pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#functional_pseudo-classes)

These pseudo-classes accept a [selector list](https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list) or [forgiving selector list](https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list#forgiving_selector_list) as a parameter.

[`:is()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:is)

The matches-any pseudo-class matches any element that matches any of the selectors in the list provided. The list is forgiving.

[`:not()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:not)

The negation, or matches-none, pseudo-class represents any element that is not represented by its argument.

[`:where()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:where)

The specificity-adjustment pseudo-class matches any element that matches any of the selectors in the list provided without adding any specificity weight. The list is forgiving.

[`:has()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:has)

The relational pseudo-class represents an element if any of the relative selectors match when anchored against the attached element.

## [Custom state pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#custom_state_pseudo-classes)

These pseudo-classes apply to custom elements.

[`:state()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:state)

Matches custom elements that have the specified custom state.

## [Page pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#page_pseudo-classes)

These pseudo-classes relate to pages in a printed document and are used with the [`@page`](https://developer.mozilla.org/en-US/docs/Web/CSS/@page) at-rule.

[`:left`](https://developer.mozilla.org/en-US/docs/Web/CSS/:left)

Represents all left-hand pages of a printed document.

[`:right`](https://developer.mozilla.org/en-US/docs/Web/CSS/:right)

Represents all right-hand pages of a printed document.

[`:first`](https://developer.mozilla.org/en-US/docs/Web/CSS/:first)

Represents the first page of a printed document.

[`:blank`](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#blank_2)

Represents a blank page in a printed document.


