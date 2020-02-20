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
      products = resp
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
</div>