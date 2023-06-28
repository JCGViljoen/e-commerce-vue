<template>
    <div>
<h2>{{ prduct.name }}</h2>
<p>Brand: {{ product.brand }}</p>
<p>Description: {{product.description}}</p>
<p>Price: {{product.Price}}</p>
<img src="product.image" alt="product.name">
    </div>
</template>

<script>
    export default {
        props: {
            product: {
                type: Object,
                required: true
            }
        }
        
    };
</script>

<style scoped>

</style>