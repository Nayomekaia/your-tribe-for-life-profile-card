<script>
  import '$lib'
	import '../app.css'; 
  </script>
  

  <main>
    <slot />
  </main>
   
<style>

  /* maak deze selectors global zodat ze NIET gescope’d worden */
  :global(body) {
  background-image: url('/concreet8.png');
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: center;
  background-size: cover;


}


</style>