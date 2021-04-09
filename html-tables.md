Here is an HTML table you can use in your Rich Text Elements or E-Commerce websites for products or simply to show data since Webflow doesn't natively support it yet.

Place into `<embed>` element
```css
<!-- HTML TABLE --> 
<style>
/* ----------------------------- TABLE STYLES ----------------------------- */
:root {
  /* TABLE COLORS */
  --table-header-font-color: #ffffff;
  --table-header-bg-color: teal;
  --table-header-border-color: #ffffff;
  
  --table-cell-font-color: #777777;
  --table-cell-border-color: #d2d2d2;
  
  --table-bg-color: #ffffff;
  --table-border-color: #ffffff; /* Most Likely won't be seen */
  
  /* TABLE DIMENSIONS */
  --table-header-padding-top-bottom: 12px; /* headers top & bottom padding */
  --table-header-padding-left-right: 10px; /* headers left & right padding */
  --table-heading-font-size: 18px;
  
  --table-cell-padding-top-bottom: 10px;  /* Cells top & bottom padding */
  --table-cell-padding-left-right: 10px;  /* Cells left & right padding */
  --table-cell-font-size: 14px;
  --table-cell-min-width: 200px;
  
  --table-margin-bottom: 48px;
}
/* ----------------------------- END OF TABLE STYLES ----------------------------- */



/* DON'T NEED TO WORRY ABOUT THESE BELOW!!! */
.table-wrap {
	overflow-x: scroll;
  width: 100%;
  margin-bottom: var(--table-margin-bottom);
}

table, th, td {
  border-collapse: collapse;
}

table {
	width: 100%;
  border: 1px solid var(--table-border-color);
  background-color: var(--table-bg-color);
}

th:last-child {
  border-left: 1px solid var(--table-header-bg-color);
  border-top: 1px solid var(--table-header-bg-color);
  border-right: 1px solid var(--table-header-bg-color);
  border-bottom: 1px solid var(--table-header-bg-color);
}

th {
	text-align: left;
  color: var(--table-header-font-color);
  background-color: var(--table-header-bg-color);
  padding: var(--table-header-padding-top-bottom) var(--table-header-padding-left-right);
  font-size: 16px;
  border-left: 1px solid var(--table-header-bg-color);
  border-top: 1px solid var(--table-header-bg-color);
  border-right: 1px solid var(--table-header-border-color);
  border-bottom: 1px solid var(--table-header-bg-color);
  font-size: var(--table-heading-font-size);
}

td {
  color: var(--table-cell-font-color);
  border: 1px solid var(--table-cell-border-color);
	padding: var(--table-cell-padding-top-bottom) var(--table-cell-padding-left-right);
  font-size: var(--table-cell-font-size);
}

th, td {
	min-width: var(--table-cell-min-width);
}
</style>



<!-- ****TABLE CONTENT**** -->
<div class="table-wrap">
  <table>
    <!-- heading Columns -->
    <tr>
      <th>Shoe Type</th>
      <th>Color</th>
      <th>Size</th>
      <th>Details</th>
    </tr>

    <!-- Row 1 -->
    <tr>
      <td>Running</td>
      <td>White/Black</td>
      <td>10.5, 11, 12</td>
      <td>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</td>
    </tr>

    <!-- Row 2 -->
    <tr>
      <td>Skateboarding</td>
      <td>Black</td>
      <td>6.5, 7, 8.5, 9, 9.5, 10.5, 12</td>
      <td>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</td>
    </tr>

    <!-- Row 3 -->
    <tr>
      <td>Hiking</td>
      <td>Tan</td>
      <td>7, 8.5, 9, 10.5, 11, 12</td>
      <td>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</td>
    </tr>
  </table>
</div>
```
