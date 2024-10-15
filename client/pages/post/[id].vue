<template>
    <main>
        <h1>{{ post.title }}</h1>
        <img :src=base_url+post.img.url :alt=post.img.alternativeText>
        <div v-html="mark"></div>
    </main>
</template>

<script setup> 
    import MarkdownIt from "markdown-it";
    const markdown = new MarkdownIt()

    const { id } = useRoute().params

    const api = await $fetch('http://localhost:1337/api/posts?populate=*')
    const post = api.data[id]
    const mark = post.body
    
    const base_url = 'http://localhost:1337'
</script>