# [tktk Module Name] - tktk Microlesson Name

![Hero image](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

## 10. The `class` Attribute

Technically, you could use those attribute methods above to work with an element's classes.

However, the [classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList) property offers a better approach. 

`classList` is an object with the following methods pertaining to classes:

- `add(className, className, ...)` 
- `remove(className, className, ...)`
- `toggle(className)`
- `contains(className)`
- `replace(oldClass, newClass)`

## 12. DOM Selection Summary

In summary, use the following to help you decide which method to use to select DOM elements:

- **`getElementById`**: Use when you need to select a single element that has an `id` assigned to it.

- **`querySelector`**: Use when you need to select a single element that **does not** have an `id`.

- **`querySelectorAll`**: Use when you need to select multiple elements.