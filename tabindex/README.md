# Tabindex

• The `tabindex` attribute let you set the behaviour of focusability for an HTML elements. 

• The control of the focusability is acheived by user pressing the `Tab` key, and occationally control by Javascript.

• Some focusable HTML elements have a default `tabindex` value of `0` set under the hood. These elements are:

```html
<a>
<area>
<button>
<frame> (Deprecated)
<iframe>
<input>
<object>
<select>
<textarea>
SVG <a> element
<summary> element that provides summary for a <details> element
```
You should not add the `tabindex` attribute to the above elements unless you intend to change the default behavior.


:warning: Warning: 

- You should only use `0` and `-1` as `tabindex` value.
- Avolid using value greater than `0`
- Avoid using css feature such as *ordering flex items* to order the element in a page. 
- Do not add `tabindex` attribute to the `<dialog>` element.
- If you use `tabindex` attribute, make sure it has a value set, otherwise the behaviour varies among user agents.

Since you only use `0` and `-1` as `tabindex` value, here is their behaviour:

- When the value of `tabindex` is **negative**, the element can not be navigated by `Tab` key. You have to use Javascript to focus on it .
  - The exact negative value doesn't matter.
  - This is useful for elements that should not be navigated to directly using the `Tab` key;  For example, when an off-screen modal window that should be focused when it comes into view, or a form submission error message that should be immediately focused when an errant form is submitted.

- When the value of `tabindex` is `0`, the sequential keyboard navigation follow their order in the document source. 

Now, if you must use `tabindex` value greater than `0`, then these elements will be focused first before the one set with`0` value.  The focus order will be defined by the value of the number. For example: `4` is focus before `5` but after `3`.  After all `tabindex` value greater than `0` is focused, the zeroed value `tabindex` elements will be focused. If multiple elements share the same positive `tabindex` value, their order relative to each other follows their position in the document source.



---

References:

- [tabindex - HTML: HyperText Markup Language | MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/tabindex) 
- [How-to: Use the tabindex attribute - The A11Y Project](https://www.a11yproject.com/posts/how-to-use-the-tabindex-attribute/) 
- [Don’t Use Tabindex Greater than 0 — Adrian Roselli](https://adrianroselli.com/2014/11/dont-use-tabindex-greater-than-0.html) 
