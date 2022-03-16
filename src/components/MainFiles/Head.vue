<template>
    <section class="header"
             @submit.prevent>
    <a href="#" class="logo">
        <img src="@/images/logo.png" alt="">
    </a>

    <nav class="navbar"
         :class="{active:isActivated}">
        <a href="#home">home</a>
        <a href="#about">about</a>
        <a href="#menu">menu</a>
        <a href="#products">products</a>
        <a href="#review">review</a>
        <a href="#contact">contact</a>
        <a href="#blogs">blogs</a>
    </nav>

    <div class="icons">
        <fa class="icon" @click="AddSearch" icon ="search" id="search-btn"/>
        <fa class="icon" @click="AddCart" icon = "shopping-cart" id="cart-btn"/>
        <fa class="icon" @click="AddMenu" icon = "bars" id="menu-btn"/>
    </div>

    <div class="search-form"
         :class="{active:isActive}">
        <input type="search" id="search-box" placeholder="search here...">
        <label for="search-box"><fa class="icon" icon ="search"/></label>
    </div>

    <div class="cart-items-container" 
         :class="{active:isOpened}">
        <div class="cart-item">
            <span><fa icon="xmark"/></span>
            <img src="/images/cart-item-1.png" alt="">
            <div class="content">
                <h3>cart item 01</h3>
                <div class="price">$15.99/-</div>
            </div>
        </div>
        <div class="cart-item">
            <span><fa icon="xmark"/></span>
            <img src="@/images/cart-item-2.png" alt="">
            <div class="content">
                <h3>cart item 02</h3>
                <div class="price">$15.99/-</div>
            </div>
        </div>
        <div class="cart-item">
            <span><fa icon="xmark"/></span>
            <img src="@/images/cart-item-3.png" alt="">
            <div class="content">
                <h3>cart item 03</h3>
                <div class="price">$15.99/-</div>
            </div>
        </div>
        <div class="cart-item">
            <span><fa icon="xmark"/></span>
            <img src="@/images/cart-item-4.png" alt="">
            <div class="content">
                <h3>cart item 04</h3>
                <div class="price">$15.99/-</div>
            </div>
        </div>
        <a href="#" class="btn">checkout now</a>
    </div> 

</section>
</template>

<script>
export default {
    name:'head-page',
    data(){
        return{
            isActive:false,
            isOpened:false,
            isActivated:false,
        }
    },
    methods:{
        AddSearch(){
            this.isActive=!this.isActive
        },
        AddCart(){
            this.isOpened=!this.isOpened
        },
        AddMenu(){
            this.isActivated=!this.isActivated
        }
    }
}
</script>

<style scoped>
.header{
    background: var(--bg);
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1.5rem 7%;
    border-bottom: var(--border);
    position: fixed;
    top:0; left: 0; right: 0;
    z-index: 1000;
}

.header .logo img{
    height: 6rem;
}

.header .navbar a{
    margin:0 1rem;
    font-size: 2rem;
    color:#fff;
    text-transform: uppercase;
}

.header .navbar a:hover{
    color:var(--main-color);
    border-bottom: .1rem solid var(--main-color);
    padding-bottom: .5rem;
}

.header .icons .icon{
    color:#fff;
    cursor: pointer;
    font-size: 2.5rem;
    margin-left: 2rem;
}

.header .icons div:hover{
    color:var(--main-color);
}



.header .search-form{
    position: absolute;
    top:100%; right: 7%;
    background: #fff;
    width: 60rem;
    height: 5rem;
    display: flex;
    align-items: center;
    transform: scaleY(0);
    transform-origin: top;
}

.header .search-form.active{
    transform: scaleY(1);
}

.header .search-form input{
    height: 100%;
    width: 100%;
    font-size: 1.6rem;
    color:var(--black);
    padding:1rem;
    text-transform: none;
}

.header .search-form label{
    cursor: pointer;
    font-size: 2.2rem;
    margin-right: 1.5rem;
    color:var(--black);
}

.header .search-form label:hover{
    color:var(--main-color);
}

.header .cart-items-container{
    position: absolute;
    top:100%; right: -100%;
    height: calc(100vh - 9.5rem);
    width: 35rem;
    background: rgba(255,255,255,.1);
    backdrop-filter: blur(5px);
    padding:0 1.5rem;
}

.header .cart-items-container.active{
    right: 0;
}

.header .cart-items-container .cart-item{
    position: relative;
    margin:2rem 0;
    display: flex;
    align-items: center;
    gap:1.5rem;
}

.header .cart-items-container .cart-item .fa-times{
    position: absolute;
    top:1rem; right: 1rem;
    font-size: 2rem;
    cursor: pointer;
    color: var(--black);
}

.header .cart-items-container .cart-item .fa-times:hover{
    color:var(--main-color);
}

.header .cart-items-container .cart-item img{
    height: 7rem;
}

.header .cart-items-container .cart-item .content h3{
    font-size: 2rem;
    color:white;
    padding-bottom: .5rem;
}

.header .cart-items-container .cart-item .content .price{
    font-size: 1.5rem;
    color:var(--main-color);
}

.header .cart-items-container .btn{
    width: 100%;
    text-align: center;
}
</style>