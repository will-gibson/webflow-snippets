This one line of CSS code will ignore any cursor (pointer) event such as clicks or hovers etc.This can be useful if you have a video or a gif that is not necessary for your users to interact with.

Place into `<head>`

```css
<!-- Ignore Cursor Events --> 
<style>
/* disable any cursor events e.g. click & hover */
.your-class-name {
	pointer-events: none;
}
</style>
```
