<script>
	import CampaignItem from "$lib/components/CampaignItem.svelte";
</script>

<h1 class="text-5xl font-bold mb-4">Campaigns</h1>

<h3 class="text-xl mb-4">
	Check out some of my favorite projects from college that had no limits.
</h3>

<!-- Grid Container -->
<div class="grid grid-cols-1 md:grid-cols-2 gap-1 items-center pb-6">
	<CampaignItem
		page="verizon"
		image="verizon n go tab centered.png"
		alt="Verizon'N Go: the perfect blend of tech, taste & saving time"
		hiddenText="Verizon"
	/>

	<CampaignItem
		page="heineken"
		image="sip with your sign tab 2.png"
		alt="Sip With Your Sign: sparking fresher connections with astrology"
		hiddenText="Heineken"
	/>

	<CampaignItem
		page="milkbar"
		image="one bite wonder.png"
		alt="One Bite Wonder: redefining self-care with Milkbar"
		hiddenText="Milkbar"
	/>

	<CampaignItem
		page="wildflower"
		image="case the seasons.png"
		alt="Case The Seasons: a phone case for every season"
		hiddenText="Wildflower Phone Cases"
	/>

</div>

<style>
</style>
