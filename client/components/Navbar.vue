<template>
    <nav>
        <ul>
            <li><nuxt-link to="/">Home</nuxt-link></li>
            <li><nuxt-link to="/about">About</nuxt-link></li>
            <li><nuxt-link to="/contact">Contact</nuxt-link></li>
        </ul>
    </nav>
</template>

<style scoped>
    ul{
        display: flex;
        gap: 10px;
        list-style: none;
    }
    li{
        margin: 0;
        padding: 10px;
        
    }
</style>