
<!--  npm install --save toastr -->

<style>
.success-button {
  background-color: green;
  color: white;
  margin: 1em
}


.info-button {
  background-color: blue;
  color: white;
  margin: 1em
}


.warning-button {
  background-color: orange;
  color: black;
  margin: 1em
}


.error-button {
  background-color: red;
  color: white;
  margin: 1em
}

.funny-button {
  border: 1px solid blueviolet; 
  margin: 1em
}

</style>


<script>
  // import toastr from "./main.js";
  import toastr from 'toastr'; // det virker selvom det kommer en fejlmelding
  import 'toastr/build/toastr.css';
  import Info from "./components/Info/Info.svelte";

  toastr.options = {
  "closeButton": true,
  "debug": false,
  "newestOnTop": false,
  "progressBar": false,
  "positionClass": "toast-top-right",
  "preventDuplicates": false,
  "onclick": null,
  "showDuration": "300",
  "hideDuration": "1000",
  "timeOut": "5000",
  "extendedTimeOut": "1000",
  "showEasing": "swing",
  "hideEasing": "linear",
  "showMethod": "fadeIn",
  "hideMethod": "fadeOut"
}
   function handleShowToast() {
    toastr.success('Hello, Anders!');
    toastr.options.positionClass = "toast-top-center";
  }

  // toast, with a title
  function handleToastWithTitle(){
    toastr.success('This is a toast with a title', 'Check this out');
    toastr.options.positionClass = "toast-top-right";
 
  };

  function handleToastWithWarning(){
    toastr.warning('You got virus!!','Warning')
  }

  
  function handleToastWithInfo(){
    toastr.info('The concept of soaking stale or leftover bread in a mixture of eggs and milk, and then cooking it, can be traced back to ancient civilizations. Various cultures have had their own versions of this dish. For example, the Romans prepared a dish called "Aliter Dulcia," which involved soaking bread in milk and frying it', "French toast origin")
  }


  function handleToastWithError(){
    toastr.error('This is an ordinary boring error. Please handle it.','Error')
  }

  function handleToastWithFunnyMessage() {
  const funnyMessages = [
    "Don't worry, toast can't dance either!",
    "This toast is toast-alicious!",
    "Toast-ally awesome!",
    "Toast the good times!",
    "You're toast-tally amazing!",
  ];

  const randomMessage = funnyMessages[Math.floor(Math.random() * funnyMessages.length)];

  toastr.success(randomMessage);
  toastr.options.positionClass = "toast-top-right";
}

</script>

<main>
  <h1>Svelte Toast</h1>
  <Info />

  <button class="success-button" on:click={handleToastWithTitle}>Toast with a title</button>

  <button class="warning-button" on:click={handleToastWithWarning}>Do you dear push this button?</button>

  <button class="info-button" on:click={handleToastWithInfo}>The origin of french toast</button>

  <button class="error-button" on:click={handleToastWithError}>Error</button>

  <button class="funny-button" on:click={handleToastWithFunnyMessage}>Funny</button>

  <button  class="success-button" on:click={handleShowToast}>Show Success</button>
</main>

