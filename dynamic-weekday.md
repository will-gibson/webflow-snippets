This snippet will generate the text dynamically for the correct weekday where ever you want in your project.

Place into `</body>`
```js
<!-- DYNAMIC WEEKDAY --> 
<script>
// for each .weekday element
document.querySelectorAll('.weekday').forEach(weekday => {
  // get today's day
  const today = new Intl.DateTimeFormat('en', {weekday:'long'}).format(new Date());
  // set it as the current text
  weekday.textContent = today;
});
</script>
```
