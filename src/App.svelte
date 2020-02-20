<script>
	import Header from './components/Header.svelte';
	import ProductList from './components/ProductList.svelte';
	import Impressum from './components/Impressum.svelte';
	import Datenschutz from './components/Datenschutz.svelte';
	import Footer from './components/Footer.svelte';

	import queryString from "query-string";

	$: pId = window.location.href.split('?')[1];

	


</script>

<Header pid={pId | 0}/>

{#if pId == "impressum"}
	<Impressum />
{:else if pId == "datenschutz"}
	<Datenschutz />
{:else}
	<ProductList />
{/if}

<Footer />