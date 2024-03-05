<script>
	import '../app.css';
	import { onMount } from 'svelte';
	import NavBar from "$lib/components/NavBar.svelte";

	onMount(() => {
		const script = document.createElement('script');
		script.src = 'https://kit.fontawesome.com/7dd54571e5.js';
		script.crossOrigin = 'anonymous';
		script.async = true;

		document.head.appendChild(script);

		return () => {
			// Cleanup script tag if the component is unmounted
			document.head.removeChild(script);
		};
	});
</script>

<svelte:head>
	<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@picocss/pico@1/css/pico.min.css" />
</svelte:head>

<NavBar />
<main class="px-4">
	<slot />
</main>


<style lang="postcss">
	:global(html, body) {
	  @apply bg-[#fff6ed];
	}
  </style>