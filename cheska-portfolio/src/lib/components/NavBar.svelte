<script>
	import { page } from '$app/stores';
	import NavBarItem from '$lib/components/NavBarItem.svelte';
	const navs = [];
	$: routeId = $page.route.id;

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
					<button
						id="dropdownDefaultButton"
						class="px-3 text-green-800 rounded md:border-0 md:hover:text-fuchsia-700 shadow-none"
						on:click={handleDropdownClick}
						class:active={routeId == '/campaigns'}>Projects</button>
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
						<i class="fa-brands fa-linkedin-in text-green-800 md:hover:text-fuchsia-700"></i>
					</a>
				</li>
			</ul>
		</div>
	</div>
</nav>

