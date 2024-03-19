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
<div class="flex flex-col min-h-screen">
    <main class="flex-1 px-60 flex flex-col items-center mt-10 mb-10 pb-4">
        <!-- Main content goes here -->
        <slot />
    </main>

    <footer class="py-6 px-12 flex justify-between items-center bg-black w-full">
		<!-- Left section -->
		<div class="flex items-center">
			<p class="text-white mb-0">&copy; Francesca Morales 2024</p>
		</div>
		
		<!-- Right section -->
		<div class="flex items-center">
			<a
				class="block px-3 rounded text-white md:border-0 md:hover:text-fuchsia-700 scale-150"
				href="https://www.linkedin.com/in/francesca-morales"
				target="_blank"
				rel="noopener noreferrer"
			>
				<i class="fa-brands fa-linkedin"></i>
			</a>
		</div>
	</footer>	
</div>




<style lang="postcss">
	:global(html, body) {
	  @apply bg-[#fff6ed];
	}
  </style>