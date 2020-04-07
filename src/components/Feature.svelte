<script>
  import { onMount } from "svelte";

  export let pid;

  let product = {};

  onMount(async()=>{
    const response = await fetch("/content.json")
    const resp = await response.json();
    if(pid === 0) {
      product = resp.find(el => el.feature === true);
    } else {
      product = resp.find(el => el.productid === pid);
    }
  });
</script>

<div class="feature">

    <div class="description">
        <div class="headline">{product.name}</div>
        <div class="by">von <strong>{product.by}</strong></div>
        <p class="unterline">{product.description}</p>
        <a href="{product.link}"><button class="featurebutton"><i class="fas fa-shopping-cart"></i> *JETZT KOSTENLOS SICHERN</button></a>
    </div>

    <img class="featureproduct" src="{product.img}" alt="Product" />
</div>