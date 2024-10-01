

<template>
    <h2>блог</h2>

    <main>
        <article v-for="(post, index) in posts" :key="post.id">
            <h3>{{ post.title }}</h3>
            <img :src=base_url+post.img.url :alt="post.img.alternative" >
            <p>{{ post.desc }}</p>
            <NuxtLink :to="'/post/' + index">Подробнее</NuxtLink>
        </article>
    </main>
</template>




<script setup>
    const api = await $fetch('http://localhost:1337/api/posts?populate=*')
    const posts = api.data

    const base_url = "http://localhost1337"
</script>

<style scoped>
    main{
        display: flex;
        gap: 10px;
    }
    article{
        background-color: #f5f5f5;
        padding: 10px;
        width: 300px;

        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }
    article img{
        width: 100%;
    }
    article p{
        height: 10px;
    }
    article a{
        display: block;
    }
</style>