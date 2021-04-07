Overview: Smooth accordion that automatically closes an accordion item when a new one is selected. All elements are handled directly in Webflow.

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

Place into `</body>`

```js
<!-- Javascript Accordion -->
<script>
// define the accordion function
var accordion = (function(){
  
  // get the accordion class
  var $accordion = $('.js-accordion');
  // get the accordion header class
  var $accordion_header = $accordion.find('.js-accordion-header');
  // get the accordion item class
  var $accordion_item = $('.js-accordion-item');
 
  // define default settings 
  var settings = {
    // animation speed
    speed: 400,
    
    // close all other accordion items if true
    oneOpen: false
  };
    
  // set the accordion function return
  return {  
    // pass configurable object literal
    init: function($settings) {  // the init function
      // on accordion header click
      $accordion_header.on('click', function() {
        // toggle accordion
        accordion.toggle($(this));
      });
      
      // update default settings with the initialization defined settings
      $.extend(settings, $settings); 
      
      // ensure only one accordion is active if oneOpen is true
      // if one accordion is open & accordions with the class active are more than one
      if(settings.oneOpen && $('.js-accordion-item.active').length > 1) {
        // remove the active class from all other accordion items except the first
        $('.js-accordion-item.active:not(:first)').removeClass('active');
      }
      
      // reveal the active accordion bodies
      $('.js-accordion-item.active').find('> .js-accordion-body').show();
    },
    toggle: function($this) { // the toggle function
      // if one accordion is open & it's not the first active accordion  
      if(settings.oneOpen && $this[0] != $this.closest('.js-accordion').find('> .js-accordion-item.active > .js-accordion-header')[0]) {
        // remove the active class & close it
        $this.closest('.js-accordion')
               .find('> .js-accordion-item') 
               .removeClass('active')
               .find('.js-accordion-body')
               .slideUp()
      }
      
      // show/hide the clicked accordion item by adding/removing active class & toggling slideUp/slideDown
      $this.closest('.js-accordion-item').toggleClass('active');
      $this.next().stop().slideToggle(settings.speed);
    }
  }
})();

// when the DOM is ready
$(document).ready(function(){
  // initialize the accordion its respective settings
  accordion.init({ speed: 300, oneOpen: true });
});
</script>
```
