<script>
	import CampaignItem from "$lib/components/CampaignItem.svelte";
</script>

<h1 class="text-5xl font-bold mb-4 text-green-800">Campaigns</h1>

<h3 class="text-xl mb-4 text-green-800">
	Check out some of my favorite projects from college that had no limits.
</h3>

<!-- Grid Container -->
<!-- <div class="grid grid-cols-1 md:grid-cols-2 gap-1 items-center pb-6"> -->
<div class="flex m-1 gap-2">
	<CampaignItem
		page="verizon"
		image="verizon n go tab centered.webp"
		alt="Verizon'N Go: the perfect blend of tech, taste & saving time"
		hiddenText="Verizon"
	/>

	<CampaignItem
		page="heineken"
		image="sip with your sign tab 2.webp"
		alt="Sip With Your Sign: sparking fresher connections with astrology"
		hiddenText="Heineken"
	/>
</div>
<div class="flex m-1 gap-2">
	<CampaignItem
		page="milkbar"
		image="one bite wonder.webp"
		alt="One Bite Wonder: redefining self-care with Milkbar"
		hiddenText="Milkbar"
	/>

	<CampaignItem
		page="wildflower"
		image="case the seasons.webp"
		alt="Case The Seasons: a phone case for every season"
		hiddenText="Wildflower Phone Cases"
	/>

</div>

<style>
</style>
