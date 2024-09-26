<template>
    <template>
        <main>
            <div>
                <img src="" alt="">
                <h1>{{ posts[$route.params.id - 1].title }}</h1>
                <p>{{ posts[$route.params.id - 1].body }}</p>
            </div>
        </main>
    </template>
</template>

<script setup>
    const dataTwice = await $fetch('https://dummyjson.com/posts') 
    const posts = dataTwice.posts
</script>

<style scoped>
    img{
        width: 100%;
        height: 240px;
        object-fit: cover;
    }
</style>