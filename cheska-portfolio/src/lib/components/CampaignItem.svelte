<script>
    export let page;
    export let image;
    export let alt;
    export let hiddenText;
</script>

<div>
    <a
    href={page}
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

</div>
