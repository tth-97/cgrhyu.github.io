---
layout: post
title: COMPUTER SCIENCE Capstone PBL(Character Motion Synthesis and Character Control) - 2022 Fall
nav-menu: false
show_tile: false
---

* Instructor: [Yoonsang Lee](../people/yoonsang-lee.html)
* Time / Location: 
  * Fri 09:00-13:00 / 502 IT.BT Building

## Course Outline

This lecture focuses on character animation among many fields of computer graphics. First, the principles for good software design will be reviewed, and then the basic concepts and practical techniques of character animation are introduced. Students will work on a programming project on each topic, presenting their implementation in front of other students, and discussing it.

## Schedule

* 1 - Course Intro
* 2 - Software Design, Refactoring, Unit Testing
* Presentation: Project 1
* 3 - Character Animation Basics, Motion Viewer
* Presentation: Project 3
* 4 - Motion Editing, Motion Synthesis
* Presentation: Project 3
* 5 - Particle Dynamics, Physics-Based Character Control
* Presentation: Project 4

## Selected Results

<div id="contents">

<script>
// https://stackoverflow.com/questions/610406/javascript-equivalent-to-printf-string-format
// First, checks if it isn't implemented yet.
if (!String.prototype.format) {
  String.prototype.format = function() {
    var args = arguments;
    return this.replace(/{(\d+)}/g, function(match, number) { 
      return typeof args[number] != 'undefined'
        ? args[number]
        : match
      ;
    });
  };
}

function dynamicallyLoadScript(url) {
    var script = document.createElement("script");  // create a script DOM node
    script.src = url;  // set its src to the provided URL

    document.head.appendChild(script);  // add it to the end of the head section of the page (could change 'head' to 'body' to add it to the end of the body section instead)
}

dynamicallyLoadScript('../pbl-projs.js');

window.onload = function () {
	var projs = pbl_projs;
	var contents_code = '';
	var showCount = 0;
	for(var i = 0; i < projs.length; i++) 
	{
		var proj = projs[i];
		var show = false;

		if(proj.year==2022 && proj.season=='fall')
			show = true;

		if(show)
		{
			if(showCount % 2 == 0)
				contents_code += '<div class="row">';

			contents_code += '<div class="6u 12u$(small)">';
			contents_code += '<br id="{0}"/><br/>'.format(proj.id);
			contents_code += '<b>{0}</b><br/>'.format(proj.title);
			contents_code += '{0}<br/>'.format(proj.authors);
			contents_code += '<div id="iframe_container"> <div id="iframe">';
			contents_code += '{0}'.format(proj.video_iframe);;
			contents_code += '</div></div>';
			contents_code += '</div>';

			if(showCount % 2 == 1 || i == projs.length-1)
				contents_code += '</div>';

			showCount += 1;
		}
	}

	var contents = document.getElementById("contents");
	contents.innerHTML = contents_code;
}


</script>

</div>
