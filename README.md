# Count-facebook-share-usign-pure-javascript
Count facebook share of any page by using pure Javascript code;
<pre>
&lt;script&gt;
//&lt;![CDATA[
//get current page URL
  var fbget =window.location.href;
  var mainfb =&#39;https://graph.facebook.com/?ids=&#39;;
  //usign facebook graph to get share count
  var fbsrc =mainfb+fbget;
 // getting data from json page usign XMLHttpRequest
  var request = new XMLHttpRequest();
request.open(&#39;GET&#39;, fbsrc, true);
request.onload = function() {
  if (request.status &gt;= 200 && request.status &lt; 400) {
    // Success!
    var data = JSON.parse(request.responseText);
    //not showing share count if it is zero
    if (data[fbget].share.share_count == 0) {}
    else { 
    //showing share count usign ID
  document.getElementById(&#39;fb-count&#39;).innerHTML+=data[fbget].share.share_count;}
  } 
};
request.send();
//]]&gt;&lt;/script&gt;
</pre>
use:
<pre>
&lt;div id=&#39;fb-count&#39;/&gt;
</pre>
To output of code
