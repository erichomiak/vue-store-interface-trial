<template>
    <div class="product-item">
        <p>{{product.title}}
        
        <button @click="$emit('del-product', product.id)" class="del">X</button></p>
        <p>{{product.description}}</p>
        <p>{{product.price}}</p>
    </div>
</template>

<script>
export default {
    name: "ProductItem",
    props: ["product"]
}
</script>

<style scoped>
    .product-item {
        background: #f3f3f3f3;
        padding: 10px;
        border-bottom: 1px #999999 solid;
    }

    .del {
        background: #ff0000;
        color: #ffffff;
        border: none;
        padding: 5px 10px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }

</style>