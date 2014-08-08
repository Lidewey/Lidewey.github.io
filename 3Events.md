---
layout: page
title: Events
---

<div style="float:left; width:55%;">
	<p>

	<a name="Events">Events</a>
<i>Info event 1</i><br>
<img src="http://www.freevector.com/site_media/preview_images/FreeVector-Business-Meeting.jpg">

<div class="posts">
  {% for post in paginator.posts %}
  <div class="post">
    <h3 class="post-title">
      <a href="{{ post.url }}">
        {{ post.title }}
      </a>
    </h3>
    <span class="post-date">{{ post.date | date_to_string }}</span>
     {{ post.content }} 
  </div>
  {% endfor %}
</div>

<div class="pagination">
  {% if paginator.next_page %}
    <a class="pagination-item older" href="{{ site.baseurl }}page{{paginator.next_page}}">Older</a>
  {% else %}
    <span class="pagination-item older">Older</span>
  {% endif %}
  {% if paginator.previous_page %}
    {% if paginator.page == 2 %}
      <a class="pagination-item newer" href="{{ site.baseurl }}">Newer</a>
    {% else %}
      <a class="pagination-item newer" href="{{ site.baseurl }}page{{paginator.previous_page}}">Newer</a>
    {% endif %}
  {% else %}
    <span class="pagination-item newer">Newer</span>
  {% endif %}
</div>

<div style="float:right; width:20%; ">

<head>
<style>
aside {color:#000099;}
b {color:#000099;}
</style>
</head>
<aside>
<style type="text/css"> 
<!-- 
span.label {color:black;width:10;height:5;text-align:center;margin-top:0;background:#ffF;font:bold 13px Arial} 
span.c1 {cursor:hand;color:black;width:10;height:5;text-align:center;margin-top:0;background:#ffF;font:bold 13px Arial} 
span.c2 {cursor:hand;color:red;width:10;height:5;text-align:center;margin-top:0;background:#ffF;font:bold 13px Arial} 
span.c3 {cursor:hand;color:#b0b0b0;width:10;height:5;text-align:center;margin-top:0;background:#ffF;font:bold 12px Arial} 
--> 
</style> 
 <aside>
<script type="text/javascript"> 
<!-- This script and many more are available free online at --> 
<!-- The JavaScript Source!! http://javascript.internet.com --> 
 
<!-- Begin 
function maxDays(mm, yyyy){ 
var mDay; 
 if((mm == 3) || (mm == 5) || (mm == 8) || (mm == 10)){ 
  mDay = 30; 
   } 
   else{ 
    mDay = 31 
    if(mm == 1){ 
      if (yyyy/4 - parseInt(yyyy/4) != 0){ 
       mDay = 28 
      } 
      else{ 
       mDay = 29 
     } 
  } 
  } 
return mDay; 
} 
function changeBg(id){ 
 if (eval(id).style.backgroundColor != "yellow" ){ 
  eval(id).style.backgroundColor = "yellow" 
 } 
 else{ 
  eval(id).style.backgroundColor = "#ffffff" 
 } 
} 
function writeCalendar(){ 
var now = new Date 
var dd = now.getDate() 
var mm = now.getMonth() 
var dow = now.getDay() 
var yyyy = now.getFullYear() 
var arrM = new Array("January","February","March","April","May","June","July","August","September","October","November","December" ) 
var arrY = new Array() 
 for (ii=0;ii<=4;ii++){ 
  arrY[ii] = yyyy - 2 + ii 
 } 
var arrD = new Array("Sun","Mon","Tue","Wed","Thu","Fri","Sat" ) 
 
var text = "" 
text = "<form name=calForm>" 
text += "<table border=1>" 
text += "<tr><td>" 
text += "<table width=100%><tr>" 
text += "<td align=left>" 
text += "<select name=selMonth onChange='changeCal()'>" 
 for (ii=0;ii<=11;ii++){ 
  if (ii==mm){ 
   text += "<option value= " + ii + " Selected>" + arrM[ii] + "</option>" 
  } 
  else{ 
   text += "<option value= " + ii + ">" + arrM[ii] + "</option>" 
  } 
 } 
text += "</select>" 
text += "</td>" 
text += "<td align=right>" 
text += "<select name=selYear onChange='changeCal()'>" 
 for (ii=0;ii<=4;ii++){ 
  if (ii==2){ 
   text += "<option value= " + arrY[ii] + " Selected>" + arrY[ii] + "</option>" 
  } 
  else{ 
   text += "<option value= " + arrY[ii] + ">" + arrY[ii] + "</option>" 
  } 
 } 
text += "</select>" 
text += "</td>" 
text += "</tr></table>" 
text += "</td></tr>" 
text += "<tr><td>" 
text += "<table border=1>" 
text += "<tr>" 
 for (ii=0;ii<=6;ii++){ 
  text += "<td align=center><span class=label>" + arrD[ii] + "</span></td>" 
 } 
text += "</tr>" 
aa = 0 
 for (kk=0;kk<=5;kk++){ 
  text += "<tr>" 
  for (ii=0;ii<=6;ii++){ 
   text += "<td align=center><span id=sp" + aa + " onClick='changeBg(this.id)'>1>" 
   aa += 1 
  } 
  text += "</tr>" 
 } 
text += "</table>" 
text += "</td></tr>" 
text += "</table>" 
text += "</form>" 
document.write(text) 
changeCal() 
} 
function changeCal(){ 
var now = new Date 
var dd = now.getDate() 
var mm = now.getMonth() 
var dow = now.getDay() 
var yyyy = now.getFullYear() 
var currM = parseInt(document.calForm.selMonth.value) 
var prevM 
 if (currM!=0){ 
  prevM = currM - 1 
 } 
 else{ 
  prevM = 11 
 } 
var currY = parseInt(document.calForm.selYear.value) 
var mmyyyy = new Date() 
mmyyyy.setFullYear(currY) 
mmyyyy.setMonth(currM) 
mmyyyy.setDate(1) 
var day1 = mmyyyy.getDay() 
 if (day1 == 0){ 
  day1 = 7 
 } 
var arrN = new Array(41) 
var aa 
 for (ii=0;ii<day1;ii++){ 
  arrN[ii] = maxDays((prevM),currY) - day1 + ii + 1 
 } 
 aa = 1 
 for (ii=day1;ii<=day1+maxDays(currM,currY)-1;ii++){ 
  arrN[ii] = aa 
  aa += 1 
 } 
 aa = 1 
 for (ii=day1+maxDays(currM,currY);ii<=41;ii++){ 
  arrN[ii] = aa 
  aa += 1 
 } 
 for (ii=0;ii<=41;ii++){ 
  eval("sp"+ii).style.backgroundColor = "#FFFFFF" 
 } 
var dCount = 0 
 for (ii=0;ii<=41;ii++){ 
  if (((ii<7)&&(arrN[ii]>20))||((ii>27)&&(arrN[ii]<20))){ 
   eval("sp"+ii).innerHTML = arrN[ii] 
   eval("sp"+ii).className = "c3" 
  } 
  else{ 
   eval("sp"+ii).innerHTML = arrN[ii] 
   if ((dCount==0)||(dCount==6)){ 
    eval("sp"+ii).className = "c2" 
   } 
   else{ 
    eval("sp"+ii).className = "c1" 
   } 
   if ((arrN[ii]==dd)&&(mm==currM)&&(yyyy==currY)){ 
    eval("sp"+ii).style.backgroundColor="#90EE90" 
   } 
  } 
 dCount += 1 
  if (dCount>6){ 
   dCount=0 
  } 
 } 
} 
//  End --> 
</script> 
 
</HEAD> 
 
<!-- ETAPE 2:INSEREZ LE CODE 2 ENTRE LES BALISES <BODY>..</BODY>  --> 
 
<BODY> 
 
<script type="text/javascript">writeCalendar()</script> 
 
</div>
 
</div>
