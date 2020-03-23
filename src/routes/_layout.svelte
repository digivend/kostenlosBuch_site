<script>
	import Header from '../components/Header.svelte';
	import Footer from "../components/Footer.svelte";

	export let segment;
</script>


<Header pid={segment | 0}/>

<main class="main">
	<slot></slot>
</main>

<Footer />