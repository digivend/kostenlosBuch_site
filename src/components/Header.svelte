<script>
  import Feature from './Feature.svelte';

  export let pid = 0;

</script>


<div class="header">
  <div class="content">
    <a href="/">
      <img class="logo" src="img/logo.webp alt="Logo von kostenlos-buch.de" />
    </a>
    <a href="https://www.facebook.com/Kostenlos-buchde-639411569839752/">
      <img class="social" src="img/facebook.webp" alt="Logo von Facebook" />
    </a>
    <a href="https://twitter.com/DeKostenlos/">
      <img class="social" src="img/twitter.webp" alt="Logo von Twitter" />
    </a>
    <a href="https://www.linkedin.com/company/42379062/">
      <img class="social" src="img/linkedin.webp" alt="Logo von Linkedin" />
    </a>
    <a href="https://t.me/kostenlosbuch">
      <img class="social" src="img/telegram.webp" alt="Logo von Telegram" />
    </a>
    <Feature pid={pid}/>
  </div>
</div>
