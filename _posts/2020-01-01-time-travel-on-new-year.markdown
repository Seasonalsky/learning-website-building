---
layout: post
title: "time travel but it's not time travel"
date: 2020-01-01 17:03:47 +0800
categories: jekyll
---
hellooooooo  

<!-- 
<img src="{{'/img/treecko.png' | relative_url}}" id="img_frame">
<img src="{{'/img/grovyle.png' | relative_url}}" id="img2">
<img src="{{'/img/sceptile.png' | relative_url}}" id="img3">
<img src="{{'/img/megasceptile.jpg' | relative_url}}" id="img4"> -->
<img src="{{'/img/treecko.png' | relative_url}}" id="img_frame">  

<button id="prevButton">Previous photo</button>
<button id="nextButton">Next photo</button>


<script>
let prevButton = document.getElementById("prevButton");
let nextButton = document.getElementById("nextButton");
let img_frame = document.getElementById("img_frame");

let photos = [
    "{{'/img/treecko.png' | relative_url}}",
    "{{'/img/grovyle.png' | relative_url}}",
    "{{'/img/sceptile.png' | relative_url}}",
    "{{'/img/megasceptile.jpg' | relative_url}}"
    ];

let position = 0;
//alert("the page has loaded")
// button.addEventListener("click", function(){
//     img_frame.src="{{ '/img/outing.jpg' | relative_url}}";
// });
window.addEventListener("keydown", function(event))
prevButton.addEventListener("click", function(){
    if (position != 0){
        position = position - 1;
        img_frame.src=photos[position];
    }
    else{//to make it go to the end and cycle through
        position = photos.length - 1;
        img_frame.src = photos[position];
    }
});
nextButton.addEventListener("click", function(){
    if (position != photos.length - 1){
        position = position + 1;
        img_frame.src=photos[position];
    }
    else{//to make it go to the start and cycle through
        position = photos.length - 1;
        img_frame.src = 0;
    }
});
//set timer with setInterval
//window.setInterval(????)
//HEY. Put the above functions into a variable, put that variable into the keydown on left and right keys, then call the functions inside.

</script>
