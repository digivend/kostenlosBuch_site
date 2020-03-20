<script>
	import Header from './components/Header.svelte';
	import ProductList from './components/ProductList.svelte';
	import Impressum from './components/Impressum.svelte';
	import Datenschutz from './components/Datenschutz.svelte';
	import About from './components/About.svelte';
	import Footer from './components/Footer.svelte';

	import queryString from "query-string";

	$: pId = window.location.href.split('?')[1];

	


</script>

<Header pid={pId | 0}/>

<div class="main">

	{#if pId == "impressum"}
		<Impressum />
	{:else if pId == "about"}
		<About />
	{:else if pId == "datenschutz"}
		<Datenschutz />
	{:else if pId == "abmelden"}
		<script id="n2g_script">!function(e,t,n,c,r,a,i){e.Newsletter2GoTrackingObject=r,e[r]=e[r]||function(){(e[r].q=e[r].q||[]).push(arguments)},e[r].l=1*new Date,a=t.createElement(n),i=t.getElementsByTagName(n)[0],a.async=1,a.src=c,i.parentNode.insertBefore(a,i)}(window,document,"script","https://static.newsletter2go.com/utils.js","n2g");var config = {"container": {"type": "div","class": "","style": ""},"row": {"type": "div","class": "","style": "margin-top: 15px;"},"columnLeft": {"type": "div","class": "","style": ""},"columnRight": {"type": "div","class": "","style": ""},"label": {"type": "label","class": "","style": ""}};n2g('create', 'm4baufab-tbrsch9z-24q');n2g('unsubscribe:createForm', config);</script>
	{:else}
		<ProductList />
		<script id="n2g_script">!function(e,t,n,c,r,a,i){e.Newsletter2GoTrackingObject=r,e[r]=e[r]||function(){(e[r].q=e[r].q||[]).push(arguments)},e[r].l=1*new Date,a=t.createElement(n),i=t.getElementsByTagName(n)[0],a.async=1,a.src=c,i.parentNode.insertBefore(a,i)}(window,document,"script","https://static.newsletter2go.com/utils.js","n2g");var config = {"container": {"type": "div","class": "","style": ""},"row": {"type": "div","class": "","style": "margin-top: 15px;"},"columnLeft": {"type": "div","class": "","style": ""},"columnRight": {"type": "div","class": "","style": ""},"label": {"type": "label","class": "","style": ""}};n2g('create', 'm4baufab-tbrsch9z-24q');n2g('subscribe:createPopup', config, 10);</script>
	{/if}
	
</div>
<Footer />
