<script>
	import { onMount } from 'svelte';

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

<h1 class="text-5xl font-bold mb-4 text-center">About Me</h1>

<h2 class="text-xl font-semi mx-0 text-center">My name is Francesca, but you can call me Cheska :)</h2>
<div class="flex justify-between mx-36 mt-8">
	<div class="pr-8 mt-10">
		<!-- Paragraphs -->
		<p class="mb-4">
			🍄🧚🏼‍♀️💫🍓 I'm a creative and enthusiastic advertising graduate from Boston University with a natural
			flair for art direction! When I'm not dreaming up the next big ad campaign I'm working as an
			Associate at <a
				class="underline"
				href="https://www.stantonchase.com/office/executive-search-firm-in-boston-united-states"
				>Stanton Chase</a
			>.
		</p>
		<p class="mb-4">Here's the rundown on me:</p>

		<!-- List -->
		<ol type="1" class="list-decimal list-inside pl-4 mb-4">
			<li>I was born & raised in New Jersey so I know a stellar bagel when I see one.</li>
			<li>I've watched the Twilight series way too many times (I'm team Edward btw).</li>
			<li>My pride & joy is my skincare routine.</li>
		</ol>

		<!-- More content if needed -->
		<p class="mb-4">
			Sure, I could tell you more about myself, but where's the fun in that? Get in touch:
		</p>
		<p class="mb-4">
			💌
			<!-- Email Icon -->
			<a href="mailto:morales.francescah@gmail.com" class="hover:underline"
				>Morales.FrancescaH@gmail.com</a
			>
			<!-- Email Link -->
		</p>
		<p>
            ☎️
			<a href="tel:+19083920222" class="hover:underline"> (908) 392-0222 </a>
		</p>
	</div>
	<div class="">
		<img class="" src="/images/cheska-grad.webp" alt="Francesca in graduation clothes" />
	</div>
</div>

