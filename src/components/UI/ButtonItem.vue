<template>
    <a href="" class="btn">
        <slot></slot>
    </a>
</template>

<script>
export default {
    name:'button-item',
    
}
</script>

<style scoped>
.btn{
    margin-top: 1rem;
    display: inline-block;
    padding:.9rem 3rem;
    font-size: 1.7rem;
    color:#fff;
    background: var(--main-color);
    cursor: pointer; 
}

.btn:hover{
    letter-spacing: .3rem;
}
</style>