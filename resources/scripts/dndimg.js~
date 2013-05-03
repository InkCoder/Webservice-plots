
// all images
	
	var imgArray = [];

$(document).ready(function() {


	var dropbox = document.getElementById("drop_visible");

	// init event handlers
	dropbox.addEventListener("dragenter", dragEnter, false);
	dropbox.addEventListener("dragexit", dragExit, false);
	dropbox.addEventListener("dragover", dragOver, false);
	dropbox.addEventListener("drop", drop, false);


// 2nd box

	var dropbox2 = document.getElementById("drop_ir");

	// init event handlers
	dropbox2.addEventListener("dragenter", dragEnter, false);
	dropbox2.addEventListener("dragexit", dragExit, false);
	dropbox2.addEventListener("dragover", dragOver, false);
	dropbox2.addEventListener("drop", drop, false);

	var prev_button = document.getElementById("pscroll");
	prev_button.onclick = onPClick;

	var next_button = document.getElementById("nscroll");
	next_button.onclick = onNClick;
	

});


function dragEnter(evt) {
	evt.stopPropagation();
	evt.preventDefault();
}

function dragExit(evt) {
	evt.stopPropagation();
	evt.preventDefault();
}

function dragOver(evt) {
	evt.stopPropagation();
	evt.preventDefault();
}

function drop(evt) {
	evt.stopPropagation();
	evt.preventDefault();

	var files = evt.dataTransfer.files;
	var count = files.length;
	// Only call the handler if 1 or more files was dropped.
	if (count > 0)
		handleFiles(files, this.id);
}


function handleFiles(files,boxname) {
	var file = files[0];
	if(boxname=="drop_visible")
	{	
		document.getElementById("dropl_visible").innerHTML = "Processing " + file.name ;
		var reader = new FileReader();
		reader.onloadend = (function(){
			return function(e){
				var img = document.getElementById("img_visible");
				document.getElementById("dropl_visible").innerHTML = "" ;
				img.src = e.target.result;
				imgArray[0]={name : file.name, value : e.target.result, type : "visible"};
				document.getElementById("result_img").src=img.src;
				document.getElementById("result_img").title=0;
		}})();
	}
	else if(boxname=="drop_ir")
	{
		document.getElementById("dropl_ir").innerHTML = "Processing " + file.name;
		var reader = new FileReader();
		reader.onloadend = (function(){
			return function(e){
				var img = document.getElementById("img_ir");
				document.getElementById("dropl_ir").innerHTML = "" ;
				img.src = e.target.result;
				imgArray[1]={name : file.name, value : e.target.result, type : "ir"};
				document.getElementById("result_img").src=img.src;
				document.getElementById("result_img").title=1;
		}})();
	}
	
	// begin the read operation
	reader.readAsDataURL(file);
	//assign images to slideshow	

}

//for slideshow purposes

function onPClick(evt){
	var Title= document.getElementById("result_img").title;
	if(Title>0)
	{
		Title--;
		document.getElementById("result_img").title=Title;
		document.getElementById("result_img").src=imgArray[Title].value;
	}
}


function onNClick(evt){
	var Title= document.getElementById("result_img").title;
	if(Title<1)
	{
		Title++;
		document.getElementById("result_img").title=Title;
		document.getElementById("result_img").src=imgArray[Title].value;
	}
}

