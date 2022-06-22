This snippet dynamically generates text for the correct weekday within your project.

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
