<script>
  import { onMount } from "svelte";

  export let pid = 0;

  let product = {};

  onMount(async()=>{
    const response = await fetch("/content.json")
    const resp = await response.json();
    if(pid === 0) {
      product = resp.find(el => el.feature === true);
    } else {
      product = resp.find(el => el.productid === pid);
      console.log(resp.find(el => {
        return el.productid === pid;
      }))
    }
    
  });
</script>

<div class="feature">

    <div class="description">
        <div class="headline">{product.name}</div>
        <p class="unterline">{product.description}</p>
        <a href="{product.link}"><button class="featurebutton">*JETZT KOSTENLOS SICHERN</button></a>
    </div>

    <img class="featureproduct" src="{product.img}" alt="Product" />
</div>