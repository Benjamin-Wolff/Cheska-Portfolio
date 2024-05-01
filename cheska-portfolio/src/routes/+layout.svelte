<script>
	import '../app.css';
	import NavBar from "$lib/components/NavBar.svelte";
</script>

<svelte:head>
	<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@picocss/pico@1/css/pico.min.css" />
</svelte:head>

<NavBar />
<div class="flex flex-col min-h-screen">
    <main class="flex-1 px-60 flex flex-col items-center mt-10 mb-10 pb-4">
        <!-- Main content goes here -->
        <slot/>
    </main>

    <footer class="py-6 px-12 flex justify-between items-center bg-black w-full">
		<!-- Left section -->
		<div class="flex items-center">
			<p class="text-white mb-0">&copy; Francesca Morales 2024</p>
		</div>
		
		<!-- Right section -->
		<div class="flex items-center">
			<a
				class="block px-3 rounded scale-150"
				href="https://www.linkedin.com/in/francesca-morales"
				target="_blank"
				rel="noopener noreferrer"
			>
			<svg class="w-3.5 h-auto fill-white hover:fill-fuchsia-700" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
				<path d="M416 32H31.9C14.3 32 0 46.5 0 64.3v383.4C0 465.5 14.3 480 31.9 480H416c17.6 0 32-14.5 32-32.3V64.3c0-17.8-14.4-32.3-32-32.3zM135.4 416H69V202.2h66.5V416zm-33.2-243c-21.3 0-38.5-17.3-38.5-38.5S80.9 96 102.2 96c21.2 0 38.5 17.3 38.5 38.5 0 21.3-17.2 38.5-38.5 38.5zm282.1 243h-66.4V312c0-24.8-.5-56.7-34.5-56.7-34.6 0-39.9 27-39.9 54.9V416h-66.4V202.2h63.7v29.2h.9c8.9-16.8 30.6-34.5 62.9-34.5 67.2 0 79.7 44.3 79.7 101.9V416z"/>
			</svg>
				<!-- <i class="fa-brands fa-linkedin text-white md:hover:text-fuchsia-700"></i> -->
		</div>
	</footer>	
</div>




<style lang="postcss">
	:global(html, body) {
	  @apply bg-[#fff6ed];
	}
  </style>