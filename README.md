[[[[[# Callback-Deep-Dive-in-JavaScript
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

# CallBack hell and what is the drwaback of callback hell?
```ruby
function stepOne(callback) {
  setTimeout(function() {
    console.log("Step one is completed");
      callback();
      }, 1000)
    }

 function stepTwo(callback) {
  setTimeout(function() {
    console.log("Step Two is completed");
      callback();
      }, 1000)
    }     
function stepThree(callback) {
  setTimeout(function() {
    console.log("Step Three is completed");
      callback();
      }, 1000)
    }  
function finalStep() {
  console.log("Step final")
  }
```
### I'm solving this issue with the help of callback which will be nested

```ruby
stepOne(function() {
stepTwo(function() {
  stepThree(function() {
  finalStep()
)
```
