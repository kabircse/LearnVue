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
