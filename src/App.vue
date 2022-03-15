<template>
    
    <div class="app">
      
      <start/>
      <home/>
      <about/>
      <products
      :prev="prev" 
      :next="next"
      :posts="posts"
      @load-next="NextData"
      @load-prev="PrevData"
      />
      <menu/>
      <review/>
      <contact/>
      <foot/>
      
        
        
        
    </div>
</template>

<script>
import About from './components/MainFiles/About.vue';
import Contact from './components/MainFiles/Contact.vue';
import Foot from './components/MainFiles/Foot.vue';
import Start from './components/MainFiles/Head.vue';
import Home from './components/MainFiles/Home.vue';
import Menu from './components/MainFiles/Menu.vue';
import Products from './components/MainFiles/Products.vue';
import Review from './components/MainFiles/Review.vue';
import axios from 'axios';

export default {
  components: { Home, Contact, About, Products, Menu, Review, Foot, Start},
  data() {
    return {
        next: "",
        prev: "",
      posts: [
        { title: "ffd", price: 1, description: "dd", image_url: 'dds'}
      ]
    }
  },
  methods:{
      async NextData(){
            try{
            const response = await axios.get(this.next);
            this.posts=response.data.results;
            this.next=response.data.next;
            this.prev=response.data.previous;
            console.log(response.data)
        } catch(e){
            alert('Error')
        }
      },
      async PrevData(){
            try{
            const response = await axios.get(this.prev);
            this.posts=response.data.results;
            this.next=response.data.next;
            this.prev=response.data.previous;
            console.log(response.data)
        } catch(e){
            alert('Error')
        }
      }
  },
    
    async mounted(){
      try{
        const response = await axios.get('http://127.0.0.1:8000/items/');
        this.posts=response.data.results;
        this.next=response.data.next;
        this.prev=response.data.previous;
        console.log(response.data)
      } catch(e){
          alert('Error')
      }
  }
}
</script>


<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@100;300;400;500;700&display=swap');

:root{
    --main-color:#d3ad7f;
    --black:#13131a;
    --bg:#010103;
    --border:.2rem solid rgba(255,255,255,.3);
}

*{
    font-family: 'Roboto', sans-serif;
    margin:0; padding:0;
    box-sizing: border-box;
    outline: none; border:none;
    text-decoration: none;
    text-transform: capitalize;
    transition: .2s linear;
}

html{
    font-size: 62.5%;
    overflow-x: hidden;
    scroll-padding-top: 9rem;
    scroll-behavior: smooth;
}

html::-webkit-scrollbar{
    width: .8rem;
}

html::-webkit-scrollbar-track{
    background: transparent;
}

html::-webkit-scrollbar-thumb{
    background: var(--main-color);
    border-radius: 5rem;
}

body{
    background: var(--bg);
}

section{
    padding:2rem 9%;
}

.heading{
    text-align: center;
    color:#fff;
    text-transform: uppercase;
    padding-bottom: 3.5rem;
    font-size: 4rem;
}

.heading span{
    color:var(--main-color);
    text-transform: uppercase;
}


#menu-btn{
    display: none;
}
.btn{
    margin-top: 1rem;
    display: inline-block;
    padding:.9rem 3rem;
    font-size: 1.7rem;
    color:#fff;
    background: var(--main-color);
    cursor: pointer; 
}
@media (max-width:991px){

    html{
        font-size: 55%;
    }

    .header{
        padding:1.5rem 2rem;
    }

    section{
        padding:2rem;
    }

}

@media (max-width:768px){

    #menu-btn{
        display: inline-block;
    }

    .header .navbar{
        position: absolute;
        top:100%; right: -100%;
        background: rgba(255,255,255,.1);
        backdrop-filter: blur(5px);
        width: 30rem;
        height: calc(100vh - 9.5rem);
        z-index: 1;
    }

    .header .navbar.active{
        right:0;
    }

    .header .navbar a{
        color:var(--black);
        display: block;
        margin:1.5rem;
        padding:.5rem;
        font-size: 2rem;
        z-index: 100;
    }

    .header .search-form{
        width: 90%;
        right: 2rem;
    }

    .home{
        background-position: left;
        justify-content: center;
        text-align: center;
    }

    .home .content h3{
        font-size: 4.5rem;
    }

    .home .content p{
        font-size: 1.5rem;
    }

}

@media (max-width:450px){

    html{
        font-size: 50%;
    }

}
</style>
