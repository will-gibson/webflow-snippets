Overview: Disable the option for any user to highlight and select an element on your web page.

Guide: Simply paste the CSS code into the </ head> custom code section of either the page's settings or the global site settings like you see below.

`<head> Code>`

```css
<!-- DISABLES TEXT SELECT -->
<style>
/* disable user selection of an element */
.noselect {
  -webkit-user-select: none; /* webkit browsers */
  -khtml-user-select: none; /* Konqueror browser */
  -moz-user-select: none; /* firefox browser */
  -ms-user-select: none; /* internet explorer & edge */
  user-select: none;
}
</style>
```
