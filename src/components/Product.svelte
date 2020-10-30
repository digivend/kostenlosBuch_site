<script>
    export let product
</script>



<div class="product content">

    <img class="image" src="{product.img}" alt="{product.alt}" />

    <div class="props">
        <h1 class="name">{product.name}</h1>
        <div class="by">von <strong>{product.by}</strong></div>
        <div class="by">Kategorie <strong>{product.category}</strong></div>
        <div class="description">{product.description}</div>
        <div class="final">
            <div class="price"><span class="old">{product.price}</span> &euro</div>
            <a class="right" href="{product.link}"><button ><i class="fas fa-shopping-cart"></i> *Jetzt kostenlos sichern</button></a>
        </div>
    </div>
</div>

<div class="divider"></div>