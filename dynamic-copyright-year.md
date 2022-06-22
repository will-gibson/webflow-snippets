This short Javascript code crumb dynamically sets the current year for your © copyright year in your footer automatically.

Place into `</body>`
```js
<!-- Dynamic Copyright Year -->
<script>
// get current year
const year = new Date().getFullYear();
// set .year's text to current year
$('.year').text(year);
</script>
```
