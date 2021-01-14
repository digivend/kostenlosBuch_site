<script>
	import Product from './Product.svelte';
	import Spinner from './Spinner.svelte';

	import fetch from 'cross-fetch';

	let color = "#FF3E00";
	let size = "60";
	let categoryList = ["Alle"];
	let filterValue = "Alle";

	let content = fetch("./content.json")
		.then( resp => resp.json())
		.then( resp => {
			resp.map(item => {
			if(categoryList.indexOf(item.category) === -1)
				categoryList.push(item.category)
			});

			return resp;
		});
		
</script>

<style>
    .productlist {
        margin-top: 50px;
        margin-bottom: 50px;
    }

		.spinner-item {
			min-width: 250px;
			min-height: 250px;
			display: flex;
			justify-content: center;
			align-items: center;
			position: relative;
		}

		.select-box {
			position: relative;
			margin: 20px;
			margin-left: 10%;
		}
</style>


<div>
	{#await content}
		
		<div class="spinner-item" title="Loading spinner">
			<Spinner size={size} color={color} />
		</div>

	{:then results}

		<div class="select-box">
			<span>Kategorien:</span>
			<select bind:value={filterValue}>
				{#each categoryList as category}
					<option value={category}>{category}</option>
				{/each}
			</select>
		</div>

		<div class="productlist">
			{#each results as product}
				{#if product.category === filterValue || filterValue === "Alle"}
					<Product {product} />
				{/if}
			{/each}
		</div>

	{:catch error}
		<pre style="color: red">
			{error.message}
		</pre>
	{/await}

	<script id="n2g_script">!function(e,t,n,c,r,a,i){e.Newsletter2GoTrackingObject=r,e[r]=e[r]||function(){(e[r].q=e[r].q||[]).push(arguments)},e[r].l=1*new Date,a=t.createElement(n),i=t.getElementsByTagName(n)[0],a.async=1,a.src=c,i.parentNode.insertBefore(a,i)}(window,document,"script","https://static.newsletter2go.com/utils.js","n2g");var config = {"container": {"type": "div","class": "","style": ""},"row": {"type": "div","class": "","style": "margin-top: 15px;"},"columnLeft": {"type": "div","class": "","style": ""},"columnRight": {"type": "div","class": "","style": ""},"label": {"type": "label","class": "","style": ""}};n2g('create', 'm4baufab-tbrsch9z-24q');n2g('subscribe:createPopup', config, 22);</script> -->
</div>