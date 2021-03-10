# LearnVue
1. State Management: Managing application states (sharing data) to different pages.
  Flux Architecture: States that state is centralized in a store and the store can't be directly mutated(changed).
  For updating a state we use dispatcher

2. Session Management: For managing user authrization token/state.

      a. Store the session in a server (database, cache, redis). This is more secure.
      
      b. Store the session in browser (cookie, localstorage). XSS vulnerable.
  
For both cases, session/state management we can use vuex.

3. For SEO:

      a. Use history instead of hash mode.
      
      b. Use VueRouter/Vue Meta, Pre rendering/serer rendering(SSR),
      
      c. SEO friendly URL
      
      d. Lazy loading instead of whole page rendering
      
      e. Mobile friendly.

3. Async: An asynchronous function is a function which operates asynchronously via the event loop, using an implicit Promise to return its result.
    * async await makes it much more easier to use promises.
    * javascript/nodejs is to think asynchronous by default
    * async await generally means you are doing things in sequential way.
    
4. Promise: Assurance that one will do something or that a particular thing will happen.    
   There are two parts of a promise.
   
   a. Creation of promises    
        new Promise( /* executor */ function(resolve, reject) { ... } );
        
   b. Handling of promises.
   
    Example:
      Promise:
      
        var promise4 = Promise.resolve(1); //Promise.reject("Not interested");
        promise4.then(function(value){
          console.log("This will run as it is a resovled promise. The resolved value is ", value);
        });
        promise4.then(function(value){
          console.log("This will also run as multiple handlers can be added. Printing twice the resolved value which is ", value * 2);
        });
        promise4.catch(function(reason){
          console.log("This will not run as it is a resolved promise", reason);
        });

        var keepsHisWord;
        keepsHisWord = true;
        promise1 = new Promise(function(resolve, reject) {
          if (keepsHisWord) {
            resolve("The man likes to keep his word");
          } else {
            reject("The man doesnt want to keep his word");
          }
        });
        console.log(promise1);
      
      Async:
      
        async function testAsync() {
          for (var i = 0; i < 5; i++) {
            try {
              result1 = await promiseTRRARNOSG();
              console.log("Result 1 ", result1);
              result2 = await promiseTRRARNOSG();
              console.log("Result 2 ", result2);
            } catch (e) {
              console.log("Error", e);
            } finally {
              console.log("This is done");
            }
          }
       }
       testAsync();
       
  When promises or async-wait:
  1. async returns a promise.
  2. await is used for calling an async function and wait for resolve or reject.
  3. await blocks the execution of the code within the async
  4. 
       
