<script>
	let campaigns = [
		{
			page: 'verizon',
			image: 'verizon n go tab centered.png',
			alt: "Verizon'N Go: the perfect blend of tech, taste & saving time",
			hiddenText: 'Verizon'
		},
		{
			page: 'heineken',
			image: 'sip with your sign tab 2.png',
			alt: 'Sip With Your Sign: sparking fresher connections with astrology',
			hiddenText: 'Heineken'
		},
		{
			page: 'milkbar',
			image: 'one bite wonder.png',
			alt: 'One Bite Wonder: redefining self-care with Milkbar',
			hiddenText: 'Milkbar'
		},
		{
			page: 'wildflower',
			image: 'case the seasons.png',
			alt: 'Case The Seasons: a phone case for every season',
			hiddenText: 'Wildflower Phone Cases'
		}
	];
</script>

<h1 class="text-5xl font-bold mb-4">Campaigns</h1>

<h3 class="text-xl mb-4">
	Check out some of my favorite projects from college that had no limits.
</h3>

<!-- Grid Container -->
<div class="grid grid-cols-1 md:grid-cols-2 gap-1 items-center pb-6">
	{#each campaigns as { page, image, alt, hiddenText }}
		<a
			href={`campaigns/${page}`}
			class="relative overflow-hidden group flex items-center justify-center"
		>
			<img
				src={`/images/${image}`}
				{alt}
				class="w-full h-auto transition duration-300 group-hover:contrast-50"
			/>
			<div
				class="absolute bottom-0 left-0 p-4 opacity-0 group-hover:opacity-100 text-left text-4xl text-green-700"
			>
				{hiddenText}
			</div>
		</a>
	{/each}
</div>

<style>
</style>
