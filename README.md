# Count-facebook-share-usign-pure-javascript
Count facebook share of any page by using pure Javascript code;
<pre>
<script>
//<![CDATA[
//get current page URL
  var fbget =window.location.href;
  var mainfb ='https://graph.facebook.com/?ids=';
  //usign facebook graph to get share count
  var fbsrc =mainfb+fbget;
 // getting data from json page usign XMLHttpRequest
  var request = new XMLHttpRequest();
request.open('GET', fbsrc, true);
request.onload = function() {
  if (request.status >= 200 && request.status < 400) {
    // Success!
    var data = JSON.parse(request.responseText);
    //not showing share count if it is zero
    if (data[fbget].share.share_count == 0) {}
    else { 
    //showing share count usign ID
  document.getElementById('fb-count').innerHTML+=data[fbget].share.share_count;}
  } 
};
request.send();
//]]></script>
</pre>
use:
<pre>
<div id='fb-count'/>
</pre>
To output of code
