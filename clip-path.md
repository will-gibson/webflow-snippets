Clip Path (Slanted Edges)

Shape the edge of your sections, buttons or other elements to give them more character with some CSS using the clip-path property.

Place within <head>


```css
/* CLIP PATH */
<style>
/* clip elements to specific shapes */
/* provide 4 values for each side in the order: top, right, bottom, left to create the polygon */
/* the calc() property is used to make calculations based on viewport  */
.cp-1{
	clip-path: polygon(0 0, 100% 0, 100% calc(100% - 10vw), 0 100%);
  -webkit-clip-path: polygon(0 0, 100% 0, 100% calc(100% - 10vw), 0 100%); /* webkit browsers */
}

.cp-2{
	clip-path: polygon(0 calc(0% + 10vw), 100% 0, 100% 100%, 0 100%);
  -webkit-clip-path: polygon(0 calc(0% + 10vw), 100% 0, 100% 100%, 0 100%); /* webkit browsers */
}

.cp-3{
	clip-path: polygon(0 0, 100% 0, 100% 90%, 50% 100%,0 100%);
  -webkit-clip-path: polygon(0 0, 100% 0, 100% 90%, 50% 100%,0 90%); /* webkit browsers */
}

.cp-4{
	clip-path: polygon(0 0, 100% 0, 100% 90%, 25% 80%, 50% 100%, 5% 80%, 0 100%);
  -webkit-clip-path: polygon(0 0, 100% 0, 100% 90%, 75% 80%, 50% 100%, 25% 80%, 0 90%); /* webkit browsers */
}

.cp-btn {
	clip-path: polygon(0 10%, 100% 0, 100% 90%, 0 100%);
  -webkit-clip-path: polygon(0 10%, 100% 0, 100% 90%, 0 100%); /* webkit browsers */
}

.cp-btn:hover {
	clip-path: polygon(0 0, 100% 0, 100% 90%, 0 90%);
  -webkit-clip-path: polygon(0 0, 100% 10%, 100% 100%, 0 90%); /* webkit browsers */
}
</style>
```
