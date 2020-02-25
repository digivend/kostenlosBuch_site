<script>
  import Feature from './Feature.svelte';

  export let pid = 0;

</script>


<div class="header">
  <div class="content">
    <a href="/">
      <img class="logo" src="img/logo.png" alt="digiVend" />
    </a>
    <a href="https://www.facebook.com/Kostenlos-buchde-639411569839752/">
      <img class="social" src="img/facebook.png" alt="facebook" />
    </a>

    <Feature pid={pid}/>
  </div>
</div>
