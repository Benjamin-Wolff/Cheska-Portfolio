<script>
    // @ts-nocheck

	import { page } from '$app/stores';
	import NavBarItem from '$lib/components/NavBarItem.svelte';
	const navs = [];
	$: routeId = $page.route.id;


	let isDropdownOpen = false; // default state (dropdown close)

	const handleDropdownClick = () => {
		isDropdownOpen = !isDropdownOpen; // togle state on click
	};

	// @ts-ignore
	const handleDropdownFocusLoss = ({ relatedTarget, currentTarget }) => {
		// use "focusout" event to ensure that we can close the dropdown when clicking outside or when we leave the dropdown with the "Tab" button
		if (relatedTarget instanceof HTMLElement && currentTarget.contains(relatedTarget)) return;
		isDropdownOpen = false;
	};
</script>

<nav id="navbar" class="border-gray-200">
	<div class="w-full flex items-center justify-between mx-auto py-5 px-8">
		<a href="/" class="flex items-center space-x-5">
			<span class="text-2xl font-medium text-green-800 whitespace-nowrap">Francesca Morales</span>
		</a>
		<div class="hidden md:flex md:items-md:w-auto" id="navbar-default">
			<ul
				class="text-sm flex flex-col p-3 md:p-0 mt-4 border border-gray-100 rounded-lg md:flex-row md:space-x-1 md:mt-0 md:border-0"
			>
				<li>
					<NavBarItem title="Home" href="/" target="_self" {routeId} />
				</li>
				<li class="relative dropdown" on:focusout={handleDropdownFocusLoss}>
					<!-- svelte-ignore a11y-click-events-have-key-events -->
					<!-- svelte-ignore a11y-no-static-element-interactions -->
					<div
						class="px-3 text-green-800 rounded md:border-0 md:hover:text-fuchsia-700 shadow-none"
						on:click={handleDropdownClick}
						class:active={routeId == '/campaigns'}>Projects</div>
					<!-- Dropdown menu -->
					<ul
						class="flex-col p-2 shadow bg-base-100 rounded-box w-40"
						style="visibility: {isDropdownOpen
							? 'visible'
							: 'hidden'}; position: absolute; top: calc(100% + 2px); left: 0;"
					>
						<li>
							<a
								href="/campaigns"
								class="text-sm text-green-800 rounded md:border-0 md:hover:text-fuchsia-700 text-left"
								target="_self">Campaigns</a
							>
						</li>
						<li>
							<a
								href="https://www.peripherymagazine.com/sexandintimacy/the-harm-of-sex-negativity"
								class="text-sm text-green-800 rounded md:border-0 md:hover:text-fuchsia-700"
								target="_blank">Content Writing</a
							>
						</li>
					</ul>
				</li>
				<li>
					<NavBarItem title="About Me" href="/about" target="_self" {routeId} />
				</li>
				<li>
					<NavBarItem
						title="Resume"
						href="/Francesca+Morales+Resume.pdf"
						target="_blank"
						{routeId}
					/>
				</li>
				<li>
					<a
						class="py-2 px-3 text-green-800 rounded md:border-0 md:hover:text-fuchsia-700"
						href="https://www.linkedin.com/in/francesca-morales"
						target="_blank"
						rel="noopener noreferrer"
					>
						<svg class="w-3 h-auto mt-0.5 fill-green-800 hover:fill-fuchsia-700" 
							 xmlns="http://www.w3.org/2000/svg" 
							 viewBox="0 0 448 450">
							<path d="M100.3 448H7.4V148.9h92.9zM53.8 108.1C24.1 108.1 0 83.5 0 53.8a53.8 53.8 0 0 1 107.6 0c0 29.7-24.1 54.3-53.8 54.3zM447.9 448h-92.7V302.4c0-34.7-.7-79.2-48.3-79.2-48.3 0-55.7 37.7-55.7 76.7V448h-92.8V148.9h89.1v40.8h1.3c12.4-23.5 42.7-48.3 87.9-48.3 94 0 111.3 61.9 111.3 142.3V448z"/>
						</svg>
					</a>
					
				</li>
				
			</ul>
		</div>
	</div>
</nav>

