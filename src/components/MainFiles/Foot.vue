<template>
    <section class="footer">

    <div class="share">
        <a href="#" class="icon"><fa-brands  icon ="facebook-f"/></a>
        <a href="#" class="icon"><fa  icon ="twitter"/></a>
        <a href="#" class="icon"><fa  icon ="instagram"/></a>
        <a href="#" class="icon"><fa  icon ="linkedin"/></a>
        <a href="#" class="icon"><fa  icon ="pinterest"/></a>
    </div>

    <div class="links">
        <a href="#home">home</a>
        <a href="#about">about</a>
        <a href="#menu">menu</a>
        <a href="#product">products</a>
        <a href="#review">review</a>
        <a href="#contact">contact</a>
        <a href="#blogs">blogs</a>
    </div>

    <div class="credit">created by <span>mr. web designer</span> | all rights reserved</div>

</section>
</template>

<script>
export default {
    name:'footer-page'
    
}
</script>

<style scoped>
.footer{
    background:var(--black);
    text-align: center;
}

.footer .share{
    padding:1rem 0;
}

.footer .share .icon{
    height: 5rem;
    width: 5rem;
    line-height: 5rem;
    font-size: 2rem;
    color:#fff;
    border:var(--border);
    margin:.3rem;
    border-radius: 50%;
}

.footer .share .icon:hover{
    background-color: var(--main-color);
}

.footer .links{
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    padding:2rem 0;
    gap:1rem;
}

.footer .links a{
    padding:.7rem 2rem;
    color:#fff;
    border:var(--border);
    font-size: 2rem;
}

.footer .links a:hover{
    background:var(--main-color);
}

.footer .credit{
    font-size: 2rem;
    color:#fff;
    font-weight: lighter;
    padding:1.5rem;
}

.footer .credit span{
    color:var(--main-color);
}
</style>