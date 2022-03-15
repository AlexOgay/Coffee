<template>
    <div class="box">
            <div class="icons">
                <a href="#" class="icon"><fa icon="shopping-cart" id="shopping-cart"/></a>
                <a href="#" class="icon"><fa icon="heart" id="heart"/></a>
                <a href="#" class="icon"><fa icon="eye" id="eye"/></a>
            </div>
            <div class="image">
                <img :src="post.image_url" alt="">
            </div>
            <div class="content">
                <h3>{{post.title}}</h3>
                <div class="stars">
                    <a href="#" class="star"><fa icon="star" id="star-icon"/></a>
                    <a href="#" class="star"><fa icon="star" id="star-icon"/></a>
                    <a href="#" class="star"><fa icon="star" id="star-icon"/></a>
                    <a href="#" class="star"><fa icon="star" id="star-icon"/></a>
                    <a href="#" class="star"><fa icon="star-half" id="star-icon"/></a>
                </div>
                <div class="price">${{post.price}}<span>$20.99</span></div>
            </div>
    </div>
</template>

<script>
export default {
    name:'card-page',
    props: {
        post:{
            type: Object,
            required:true
        }
    }
}
</script>

<style scoped>
.box{
    text-align: center;
    border:var(--border);
    padding: 2rem;
}

.box:hover{
    transform: translateY(-1rem);
}

.box .icons .icon{
    height: 5rem;
    width: 5rem;
    line-height: 5rem;
    font-size: 2rem;
    border:var(--border);
    color:#fff;
    margin:.3rem;
}

.box .icons .icon:hover{
    background:var(--main-color);
}

.box .image{
    position: relative;
    height: 25rem;
}

.box .image img{
    position: absolute;
    right: 10%;
    height: 25rem;
    width: 20rem;
}

.box .content h3{
    color:#fff;
    font-size: 2.5rem;
}

.box .content .stars{
    padding: 1.5rem;
}

.box .content .stars .star{
    font-size: 1.7rem;
    color: var(--main-color);
}

.box .content .price{
    color:#fff;
    font-size: 2.5rem;
}

.box .content .price span{
    text-decoration: line-through;
    font-weight: lighter;
    font-size: 1.5rem;
}

</style>