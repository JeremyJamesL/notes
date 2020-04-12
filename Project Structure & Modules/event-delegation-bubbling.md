# Event Delegation, Bubbling and Target Elements

## Event Bubbling

When an event is fired, or triggered on a target element, for instance on a `<button>Button</button>` element. Then it is also triggered on all the parent elements of the Target Element.

![event bubbling!](/images/event-bubbling.jpg)

The event is fired on the `<button>` element, yet the event fires on all parent elements, all the way to the root `<html>` element.

The target element is stored as a property in the `event` object.

Therefore, all parent elements on which the event will also fire, will know the target element of the event.

## Event Delegation

If the event bubbles up in the DOM Tree, and all parent elements know where the event was fired, then we can simply attach an event handle to a parent element, and wait for the event to 'bubble up'.

This is called `event delegation`.

In the above example. We could attach the event to the parent `<main>` and catch the event there.

We can then act on the element we are interested in by using the target element property, which is stored in the event object.

### Use Cases for Event Delegation

1. When we have an element with lots of child elements that we are interested in. 

2. When we want an event handler attached to an element that is not yet in the DOM when our page is loaded.