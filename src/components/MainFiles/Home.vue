<template>
    <section class="home" 
    id="home" 
    :style="{'background-image': `url(${require('@/images/home-img.png')})`}">
    <div class="content">
        <h3>fresh coffee in the morning</h3>
        <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Placeat labore, sint cupiditate distinctio tempora reiciendis.</p>
        <a href="#" class="btn">get yours now</a>
    </div>

</section>
</template>

<script>
export default {
    name: 'home-page',
    data() {
    return {
      
    };
  }
}
</script>

<style scoped>
.home{
    min-height: 100vh;
    display: flex;
    align-items: center;
    background-size: cover;
    background-position: center;
}

.home .content{
    max-width: 60rem;
}

.home .content h3{
    font-size: 6rem;
    text-transform: uppercase;
    color:#fff;
}

.home .content p{
    font-size: 2rem;
    font-weight: lighter;
    line-height: 1.8;
    padding:1rem 0;
    color:#eee;
}
</style>