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
    <a href="https://twitter.com/DeKostenlos/">
      <img class="social" src="img/twitter.png" alt="twitter" />
    </a>
    <a href="https://www.linkedin.com/company/42379062/">
      <img class="social" src="img/linkedin.png" alt="linkedin" />
    </a>
    <a href="t.me/kostenlosbuch">
      <img class="social" src="img/telegram.png" alt="telegram" />
    </a>
    <Feature pid={pid}/>
  </div>
</div>
