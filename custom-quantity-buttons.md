Add really nice custom buttons for your products quantity field. This is great so users don't have to type the amount anymore.

Place into `<head>`

```css
<!-- CUSTOM QUANTITY BUTTONS -->
<style>
/* remove form styles & set margin at 0 */
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
	-webkit-appearance: none;
	margin: 0;
}
</style>
```

Place into `</body>`
```js
<!-- CUSTOM QUANTITY BUTTONS --> 
<script>
// attach click event to document that then delegates to the '+' increase button
// this ensures the click event works on dynamically added '+' buttons
$(document).on('click', '.q-inc', function(){
  // get the input field that displays the number of items
  var $input = $(this).closest('.QUANTITY-GROUP-CLASS').find('.QUANTITY-NUMBER-FIELD-CLASS');
  // get its current value 
  var val = parseInt($input.val(), 10);
  // add one to the current value
  $input.val(val + 1);
  // dispatch the 'change' event on the input field to update the cart's total items value
  $input[0].dispatchEvent(new Event('change'));
});

// attach click event to document that then delegates to the '-' decrease button
// this ensures the click event works on dynamically added '-' buttons
$(document).on('click', '.q-dec', function(){
  // get the input field that displays the number of items
  var $input = $(this).closest('.QUANTITY-GROUP-CLASS').find('.QUANTITY-NUMBER-FIELD-CLASS');
  // get its current value 
  var val = parseInt($input.val(), 10);
  // minus one from the current value while it's more than one
  // the value never goes below 1
  $input.val(Math.max(val - 1, 1));
  // dispatch the 'change' event on the input field to update the cart's total items value
  $input[0].dispatchEvent(new Event('change'));
});
</script>
```
