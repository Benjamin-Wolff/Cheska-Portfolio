<script>
	import { page } from '$app/stores';
	import NavBarItem from "$lib/components/NavBarItem.svelte";
	const navs = [
		
	];
	$: routeId = $page.route.id;

	import { onMount } from 'svelte';

	onMount(() => {
		const script = document.createElement('script');
		script.src = 'https://kit.fontawesome.com/7dd54571e5.js';
		script.crossOrigin = 'anonymous';
		script.async = true;

		document.head.appendChild(script);

		// Toggle dropdown visibility
		document.addEventListener('click', function(event) {
		const dropdownButton = document.getElementById('dropdownDefaultButton');
		const dropdownMenu = document.getElementById('dropdown');
		if (dropdownButton && dropdownMenu && event.target !== dropdownButton && !dropdownMenu.contains(event.target)) {
			dropdownMenu.classList.add('hidden');
		}
		});

		function toggleDropdown() {
			const dropdownMenu = document.getElementById('dropdown');
			dropdownMenu.classList.toggle('hidden');
		}

		return () => {
			// Cleanup script tag if the component is unmounted
			document.head.removeChild(script);
		};
	});

	
</script>

<nav id="navbar" class="border-gray-200">
    <div class="w-full flex items-center justify-between mx-auto py-5 px-7">
        <a href="/" class="flex items-center space-x-5">
            <span class="text-2xl font-medium text-black whitespace-nowrap">Francesca Morales</span>
        </a>
        <div class="hidden md:flex md:items-md:w-auto" id="navbar-default">
            <ul
                class="text-sm flex flex-col p-3 md:p-0 mt-4 border border-gray-100 rounded-lg md:flex-row md:space-x-1 md:mt-0 md:border-0"
            >
			<li>
				<NavBarItem
					title="Home"
					href="/"
					target="_self"
					routeId={routeId}
				/>
			</li>
		
			<li>
				<NavBarItem
					title="Campaigns"
					href="/campaigns"
					target="_self"
					routeId={routeId}
				/>
			</li>
		
			<li>
				<NavBarItem
					title="Content Writing"
					href="https://www.peripherymagazine.com/sexandintimacy/the-harm-of-sex-negativity"
					target="_blank"
					routeId={routeId}
				/>
			</li>
		
			<li>
				<NavBarItem
					title="About Me"
					href="/about"
					target="_self"
					routeId={routeId}
				/>
			</li>
		
			<li>
				<NavBarItem
					title="Resume"
					href="/Francesca+Morales+Resume.pdf"
					target="_blank"
					routeId={routeId}
				/>
			</li>
                <li class="relative">
                    <button id="dropdownDefaultButton" class="py-2 px-3 text-gray-900 rounded md:border-0 md:hover:text-fuchsia-700" type="button">Projects</button>
                        
                        <!-- Dropdown menu -->
                        <div id="dropdown" class="z-10 hidden bg-white divide-y divide-gray-100 rounded-lg shadow w-44 dark:bg-gray-700 absolute top-full mt-1">
                            <ul class="py-2 text-sm text-gray-700 dark:text-gray-200" aria-labelledby="dropdownDefaultButton">
                              <li>
                                <a href="/campaigns" 
                                class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Campaigns</a>
                              </li>
                              <li>
                                <a href='https://www.peripherymagazine.com/sexandintimacy/the-harm-of-sex-negativity' 
                                class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Content Writing</a>
                              </li>
                            </ul>
                        </div>
                </li>
            </ul>
        </div>
    </div>
</nav>

