Smooth accordion that automatically closes an accordion item when a new one is selected. All elements are handled directly in Webflow.

Place into `<head>`

```css
<!-- Javascript Accordion Styles -->
<style>
/* Style the According Arrow */
.accordion__item > .accordion-header > .chev-icon {
  /* set transition and transform */
  transition: .4s all;
  transform: rotate(0deg);
}

/* set the transform of the active accordion's arrow */
.accordion__item.active > .accordion-header > .chev-icon {
  transform: rotate(-180deg);
}

/* accordion item image fill color */
.accordion_item-image {
  fill: #FF8E63;
}
</style>
```
