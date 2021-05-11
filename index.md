<script> 
document.cookie = "session=test GDPR"; 
document.cookie = "favorite_task=collect Data"; 
function alertCookie() { 
  alert(document.cookie); 
  } 

document.cookie = "test1=Hello";
document.cookie = "test2=World";

const cookieValue = document.cookie
  .split('; ')
  .find(row => row.startsWith('test2='))
  .split('=')[1];

function alertCookieValue() {
  alert(cookieValue);
}

function doOnce() {
  if (!document.cookie.split('; ').find(row => row.startsWith('doSomethingOnlyOnce'))) {
    alert("Do something here!");
    document.cookie = "doSomethingOnlyOnce=true; expires=Fri, 31 Dec 9999 23:59:59 GMT";
  }
}

function resetOnce() {
  document.cookie = "doSomethingOnlyOnce=; expires=Thu, 01 Jan 1970 00:00:00 GMT";
}

</script>
<body> Apasa butonul <button onclick="alertCookie()">Show cookies</button> 
<button onclick="alertCookieValue()">Show cookie value</button> 
<button onclick="doOnce()">Only do something once</button>
<button onclick="resetOnce()">Reset only once cookie</button> </body>
