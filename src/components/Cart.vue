<template>
<div>
    <h2>Books in Cart</h2>
    <div v-bind:key="book.bookid" v-for="book in cart">
        <CartItem v-bind:book="book" v-on:decrease:cartitem="Decrease" />
    </div>
</div>
</template>

<script>
import CartItem from './CartItem.vue';
export default {
    name: "Cart",
    props: ["cart"],
    components: {
        CartItem
    },
    methods:{
        Decrease(bookId){
            this.$emit("decrease:cart",bookId);
        }

    }

}
</script>

<style scoped>
.book-item {
    background: #ffffff;
    padding: 10px;
    border-bottom: 1px rgb(201, 199, 199) dotted;
}
</style>
