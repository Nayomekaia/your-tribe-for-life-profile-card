<script>
	import favicon from '$lib/assets/favicon.svg';
	import '../app.css'; 
	export let children;
  </script>
  
  <svelte:head>
	<link rel="icon" href={favicon} />
  </svelte:head>
  
  <slot />
  
