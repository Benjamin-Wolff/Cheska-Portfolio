<script>
    import { page } from "$app/stores";
    const navs = [
        {
            title: "Home",
            href: "/",
            target: "_self"
        },
        {
            title: "Campaigns",
            href: "/campaigns",
            target: "_self"
        },
        {
            title: "Content Writing",
            href: "https://www.peripherymagazine.com/sexandintimacy/the-harm-of-sex-negativity",
            target: "_blank"
        },
        {
            title: "About Me",
            href: "/about",
            target: "_self"
        },
        {
            title: "Resume",
            href: "https://static1.squarespace.com/static/63f6179f1f72bf6dc9b7c0e5/t/65b58100d0362e2748516e12/1706393856973/Francesca+Morales+Creative+Resume+%282%29.pdf",
            target: "_blank"
        }
    ]
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
</script>   

<nav id="navbar" class="border-gray-200">
	<div class="w-full flex items-center justify-between mx-auto py-10 px-14">
	  <a href="/" class="flex items-center space-x-5">
		<span class="text-2xl font-medium text-black whitespace-nowrap">Francesca Morales</span>
	  </a>
	  <div class="hidden w-full md:flex md:items-md:w-auto" id="navbar-default">
		<ul class="font-small flex flex-col p-4 md:p-0 mt-4 border border-gray-100 rounded-lg md:flex-row md:space-x-4 md:mt-0 md:border-0">      
            {#each navs as {title, href, target}}
            <li>
			<a {href} {title}
			class="block py-2 px-3 text-gray-900 rounded md:border-0 md:hover:text-fuchsia-700" {target} rel="noopener noreferrer"
            class:active={routeId == href} >{title}</a>
		  </li>
          {/each}
          <li> <a class="block py-2 px-3 text-gray-900 rounded md:border-0 md:hover:text-fuchsia-700" 
            href="https://www.linkedin.com/in/francesca-morales" target="_blank" rel="noopener noreferrer"> <i class="fa-brands fa-linkedin-in"></i>  </a></li>
		</ul>
	  </div>
	</div>
</nav>

<style>
    .active {
        text-decoration: underline;
    }    
</style>