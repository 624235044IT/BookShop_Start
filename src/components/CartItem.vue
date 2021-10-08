<template>
<div class="book-item" v-bind:class="{'is-complete':book.completed}">

    <b>{{book.title}}</b><br />
    <b>Price:</b> {{book.price}}<br />
    <b>Qty:</b> {{book.qty}}<br />
    <div align="center">
        <button class="btn btn-success">&nbsp;+&nbsp;</button>&nbsp;
        <button class="btn btn-info" v-on:click="Decrease(book.bookid)">&nbsp;-&nbsp;</button>&nbsp;
        <button class="btn btn-danger">&nbsp;x&nbsp;</button>
    </div>

</div>
</template>

<script>
export default {
    name: "CartItem",
    props: ["book"],
    methods:{
        Decrease(bookId){
            this.$emit("decrease:cartitem",bookId);
        }
    }

}
</script>

<style scoped>
.book-item {
    background: #e6f7ff;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
}
</style>
