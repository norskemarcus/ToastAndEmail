
<!--  npm install --save toastr -->

<script>
  // import toastr from "./main.js";
  import toastr from 'toastr'; // det virker selvom det kommer en fejlmelding
  import 'toastr/build/toastr.css';

  import Info from "./components/Info/Info.svelte";

   // Event handler for showing toast notifications
   function handleShowToast() {
    toastr.success('Hello, Svelte Toast Notification!');
    console.log(toastr);
console.log(toastr.options);
  }
</script>

<main>
  <h1>Svelte Toast Notification Example</h1>
  <Info />
  <button on:click={handleShowToast}>Show Toast</button>
</main>
