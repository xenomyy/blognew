<template>
    <header>
        <h2>Главная страница</h2>
    </header>
    <main>
        <article v-for="(post,index) in posts" :key="post.id>
            {{ posts.title }}
            <img src='https://i.pinimg.com/originals/8e/57/86/8e578585b383dc11b'> 
            <ul> 
                <li v-for="tag in post.tags" :key="tag.id">
                    {{  tag  }}
                </li>
            </ul>
            <nuxt-link to="/post/"+index>Подробнее</nuxt-link>
        </article>
    </main>
</template>



<style scoped>
    main{
        display: grid;
        grid-template-columns: repeat(auto-fit,minmax(300px,1fr));
        gap: 20px;
    }
    article{
        border-radius: 10px;
        background-color: brown;
        color: wheat;
        padding: 10px; 
        
        display: grid;
        grid-template-columns: repeat(4,1fr);
        gap: 20px;
        justify-content: space-between;
    }
    article h3{
        height: -webkit-fill-available;

    }
    article img{
        width: 100%;
        height: 180px;
        object-fit: cover;
    }
    article a{
        padding: 10px;
        background-color: wheat;
        color: brown;
        text-align: center;
        text-decoration: none;
        display: block;
    }
</style>

<script setup>
  const dataTwice = await $fetch('https://dummyjson.com/posts') 
  const posts = dataTwice.posts
</script>