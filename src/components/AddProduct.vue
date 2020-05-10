<template>
    <div>
        <form @submit="addProduct">
            <input type="text" v-model="title" name="title" placeholder="Product Name">
            <input type="text" v-model="description" name="description" placeholder="Product Description">
            <input type="text" v-model="price" name="price" placeholder="Product Price">
            <input type="submit" value="Submit" class="btn">
        </form>

    </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';

export default {
    name: "AddProduct",
    data() {
        return{
            title: '',
            price: '',
            description: ''
        } 
    }, 
    methods: {
        addProduct(e) {
            e.preventDefault();
            const newProduct = {
                id: uuidv4(),
                title: this.title,
                price: this.price,
                description: this.description
            }
            this.$emit('add-product', newProduct);

            this.title = '';
            this.price = '';
            this.description = '';
        }
    }
}
</script>

<style scoped>
    form {
        display: flex;
        width: 90%;
        margin: auto;
    }

    input[type="text"] {
        flex: 10;
        padding: 5px;
    }

    input[type="submit"] {
        flex: 2;
    }
</style>