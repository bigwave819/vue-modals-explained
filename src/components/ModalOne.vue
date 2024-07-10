<template>
    <div class="backdrop" @click="closeModal">
        <div class="modal" :class="{ sales: theme === 'sales' }">
            <slot></slot>
        </div>
    </div>
</template>
<script>
export default {
    props: ['header', 'text','theme'],
    methods: {
        closeModal() {
            this.$emit('close')
        }
    }
}
</script>
<style>
.modal{
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
}
.backdrop{
    width: 100%;
    height: 100%;
    top: 0;
    position: fixed;
    background: rgba(0, 0, 0, 0.3);
}
h1{
    padding: 0;
    color: #03cfb4;
    border: none;
}
.modal.sales{
    background: crimson;
    color: white;
}
.modal.sales h1{
    color: white;
}
</style>