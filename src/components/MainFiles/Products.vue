<template>
    <section class="products" id="products">

    <h1 class="heading"> our <span>products</span> </h1>

    <div class="box-container">
        <cards-page 
        v-for="post in posts"
        :post='post'
        :key='post.id'/>
    </div>
    <div class="btn-container">
        <button class="btn" @click="$emit('LoadNext')">Load next...</button>
        <button class="btn" @click="$emit('LoadPrev')">Load prev...</button>
    </div>

</section>
</template>

<script>
import CardsPage from '../UI/CardsPage.vue'
export default {
  components: { CardsPage },
    name:'products-page',
    
    props:{
        posts:{
            type: Array,
            required: true
        },
        next:{
            type:String,
            required:false
        },
        prev:{
            type:String,
            required:false
        }
    }
}
</script>

<style scoped>
.products .box-container{
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(30rem, 1fr));
    gap:1.5rem;
}
.products .btn-container{
    display: flex;
    justify-content: space-around;
}

</style>