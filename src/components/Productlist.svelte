<script>
	import { onMount } from "svelte";
	import Product from './Product.svelte';

	let products = [];

	let itemPerLoad = 5;

	$: loaded = itemPerLoad
	$: loadedItems = products.slice(0, loaded);

	onMount(async()=>{
		const response = await fetch("/content.json")
		const resp = await response.json();
		products = resp;
		products.reverse();
	});

	function loadmore() {
		loaded += itemPerLoad;
	}

</script>

<style>
    .productlist {
        margin-top: 50px;
        margin-bottom: 50px;
    }
</style>


<div class="productlist">
    {#each loadedItems as product}
        <Product {product} />
    {/each}

    {#if loaded < products.length}
        <button class="laodmore" on:click={loadmore}>Mehr laden</button>
    {/if}

	<script id="n2g_script">!function(e,t,n,c,r,a,i){e.Newsletter2GoTrackingObject=r,e[r]=e[r]||function(){(e[r].q=e[r].q||[]).push(arguments)},e[r].l=1*new Date,a=t.createElement(n),i=t.getElementsByTagName(n)[0],a.async=1,a.src=c,i.parentNode.insertBefore(a,i)}(window,document,"script","https://static.newsletter2go.com/utils.js","n2g");var config = {"container": {"type": "div","class": "","style": ""},"row": {"type": "div","class": "","style": "margin-top: 15px;"},"columnLeft": {"type": "div","class": "","style": ""},"columnRight": {"type": "div","class": "","style": ""},"label": {"type": "label","class": "","style": ""}};n2g('create', 'm4baufab-tbrsch9z-24q');n2g('subscribe:createPopup', config, 10);</script>
</div>