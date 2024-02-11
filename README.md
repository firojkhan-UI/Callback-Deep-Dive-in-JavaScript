# Callback-Deep-Dive-in-JavaScript
Callback Deep Dive in JavaScript

```ruby
function getAPIRequest(callbackOnSuccess){
  var getReq = new XMLHttpRequest();
    getReq.open("GET", "https://reqres.in/api/users?page=2");
    getReq.send();
    getReq.onload = () => {
      if(getReq.status == 200){
        callbackOnSuccess(getReq);
      }
    }
  }

function processSucessResponse(request){
  console.log("The response is " + request.response);
}
getAPIRequest(processSucessResponse);
```
