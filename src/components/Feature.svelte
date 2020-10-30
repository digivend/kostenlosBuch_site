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
        <span class="digichoice">
          <span class="digichoice-label">Kostenlos-Buch &nbsp;<span class="digichoice-secondtext">Choice</span> </span> 
          <span class="digichoice-triangle"></span>
        </span>
        <!-- 
        <div class="headline">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam vehicula, augue eget sodales hendrerit, odio est finibus metus, a pellentesque ipsum enim sed nisi.</div>
        -->
        <div class="by">von <strong>{product.by}</strong></div>
        <p class="unterline">{product.description}</p>
        <a href="{product.link}"><button class="featurebutton"><i class="fas fa-shopping-cart"></i> *JETZT KOSTENLOS SICHERN</button></a>
    </div>

    <img class="featureproduct" src="{product.img}" alt="Product" />
</div>