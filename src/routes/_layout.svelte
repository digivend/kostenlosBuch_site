<script>
	import Header from '../components/Header.svelte';
	import Footer from "../components/Footer.svelte";

	export let segment;

	if (segment.indexOf("&") != -1) {
		segment = segment.split('&')[0];
	}
</script>


<Header pid={segment | 0}/>

<main class="main">
	<slot></slot>
</main>

<Footer />