
<script>
    /**
	 * @type {string}
	 */
     export let title;
    /**
	 * @type {string}
	 */
    export let href;
    /**
	 * @type {string}
	 */
    export let target;
    /**
	 * @type {string}
	 */
    export let routeId;

</script>

<a
    {href}
    {title}
    class="py-2 px-3 text-green-800 rounded md:border-0 md:hover:text-fuchsia-700"
    {target}
    rel="noopener noreferrer"
    class:active={routeId == href}>{title}
</a>

