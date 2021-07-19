---
layout: post
title: COMPUTER SCIENCE Capstone PBL(Character Motion Synthesis and Character Control) - 2021 Spring
nav-menu: false
show_tile: false
---

* Instructor: [Yoonsang Lee](../people/yoonsang-lee.html)
* Teaching Assistant: [Geuntae Park](../people/geuntae-park.html)
* Time / Location: 
  * Live online lectures and labs due to the COVID-19 pandemic.
  * Fri 09:00-13:00 / Online (originally 607 IT.BT Building)

## Course Outline

This lecture focuses on character animation among many fields of computer graphics. First, the principles for good software design will be reviewed, and then the basic concepts and practical techniques of character animation are introduced. Students will work on a programming project on each topic, presenting their implementation in front of other students, and discussing it.

## Schedule

* Software Design Principle, Presentation for Project 1
* Understanding Motion Data, Software Design for Motion Viewer, Presentation for Project 2
* Forward Kinematics, Inverse Kinematics, Presentation for Project 3
* Motion Warping, Stitching, Blending, Presentation for Project 4
* Particle Dynamics, Presentation for Project 5
* Rigid Body Dynamics, Character Simulation & Control, Presentation for Project 6

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

		if(proj.year==2021 && proj.season=='spring')
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
