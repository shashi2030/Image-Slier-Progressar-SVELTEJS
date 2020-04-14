<script>
import Horizontalslider from '../../templates/horizontalslider/horizontalslider.svelte';
import { onMount, beforeUpdate, afterUpdate } from 'svelte';
import Progressbar from './progressbar.svelte';
import Data from './data.json';

/* keyeventhandlar */
let key;
let keyCode;

function handleKeydown(event) {
	key = event.key;
	keyCode = event.keyCode;
	switch(keyCode){
		case 39:
			rightSlider();
		break;
		case 37:
			leftSlider();
		break;
		default:
		break;
	}
}

/*slider function */
let itemWidth = 300;
let totalLength = Data.sliderData.length-4;
let currentSlide = 0;
let animatePos = 0;
let progressLength = 0;
function rightSlider(){	
	if(currentSlide < totalLength){			
		currentSlide++;			
		animatePos -=itemWidth;	
		progressbar();	
	}	
}
function leftSlider(){
	if(currentSlide >= 1){
		currentSlide--;
		animatePos +=itemWidth;
		progressbar();
	}
}
function progressbar(){
	progressLength = (100 * currentSlide) / totalLength;
}
var updateStartTime =0;
var updateEndTime = 0;
beforeUpdate(() => {
		updateStartTime = (new Date).getTime();
});
afterUpdate(() => {
	updateEndTime = (new Date).getTime();
	var diffTime = updateEndTime - updateStartTime;
	console.log(updateStartTime);
	console.log(updateEndTime);
	console.log(updateEndTime - updateStartTime);
});

</script>
<style>
.wrapper{
	width:1200px;
	margin:0 auto;
}
</style>
<div class="wrapper">
	<Horizontalslider sliderData={Data.sliderData} animPos={animatePos} currentSlide={currentSlide} />
	<Progressbar progressLen={progressLength} />
	
</div>
<svelte:window on:keydown={handleKeydown} />