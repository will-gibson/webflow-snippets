This code will reset your Webflow form after submit without hiding the form and still showing your success message. This is great for multiple submissions for different use cases.

Place into `</body>`

```javascript
<!-- RESET WEBFLOW FORM AFTER SUBMIT --> 
<script>
// when the DOM is ready
$(function() {
  /*** START SCRIPT CONFIG ***/

  // Replace with value for your form. ie. "#your-form-id" or ".your-form-class"
  var FORM_SELECTOR = ".your-class";

  // Do you want to hide the success message after the form is submitted?
  var HIDE_SUCCESS_MESSAGE = false;
  
  // Do you want the success message to show above the form?
  var SUCCESS_MESSAGE_ABOVE_FORM = true;

  /*** END SCRIPT CONFIG ***/

  // define the resetCustomElement function
  var resetCustomElement = function(customElement) {
    // get the input element
    var inputElement = customElement.nextSibling;
    // if it's checked
    if (inputElement.checked) {
      // add the class "w--redirected-checked"
      customElement.classList.add("w--redirected-checked");
    } else {  // if not checked
      // remove the class "w--redirected-checked"
      customElement.classList.remove("w--redirected-checked");
    }
  };

  // define the resetForm function
  var resetForm = function(form, successDiv) {
    // Reset the inputs in the form
    form.reset();

    // Reset custom checkboxes
    document.querySelectorAll(".w-checkbox-input--inputType-custom").forEach(resetCustomElement);

    // Reset custom radio buttons
    document.querySelectorAll(".w-form-formradioinput--inputType-custom").forEach(resetCustomElement);

    // Show the form
    form.style.display = "block";

    // Hide Success Message
    if (HIDE_SUCCESS_MESSAGE) {
      successDiv.style.display = "none";
    }
  };

  // get the form
  var form = document.querySelector(FORM_SELECTOR);
  // get the successdiv
  var successDiv = form.nextSibling;
  
  // If we are not hiding the success message AND we want the message above the form
  if (!HIDE_SUCCESS_MESSAGE && SUCCESS_MESSAGE_ABOVE_FORM) {
    // Move the form last so that the success message appears before it
    form.parentElement.appendChild(form);
  }

  // Create an observer to run our resetForm function when Webflow hides our form after submission
  var observer = new MutationObserver(function(mutations) {
    // if the form's display is set to none
    if (form.style.display === "none") {
      // call the resetForm function
      resetForm(form, successDiv);
    }
  });

  // Listen for when the style attribute of our form changes
  observer.observe(form, { attributes: true, attributeFilter: ["style"] });
});
</script>
```
