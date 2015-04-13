---
layout: default
title: "About"
---

<div id="about"></div>

<form id="mtxform" name="mtxform">
	<span id="inputext" class="hidden">
	<textarea rows="6" cols="46" id="text" name="text">
	出生年代 Birth: 传说中的1988
	工作时间 Working Time: 2010.07
	技术 IT Skills: Java/Web/Hadoop/Nosql/Shell
	目前工作 Now: RD@JD
	梦想：只想安静做一个美男子
	</textarea>
	</span>
</form>

<!-- Blog Comments -->
<div class="media">
  <!-- UY BEGIN -->
  <div id="uyan_frame">
  </div>
  <script type="text/javascript" src="http://v2.uyan.cc/code/uyan.js?uid=1511840">
  </script>
  <!-- UY END -->
</div>

<script type="text/javascript" src="js/about.js"></script>
<script src="js/jquery-1.11.0.js"></script>
<script type="text/javascript">
            $(document).ready(function(){
                document.getElementById('about').style['height'] = document.documentElement.clientHeight - document.getElementById('box').offsetHeight - 60 + 'px';
                mtx.init("about", 800, 150, [255,255,255], [255,64,0], [44,44,44]);
            });
</script>