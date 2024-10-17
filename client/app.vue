<template>
  <NuxtLoadingIndicator duration="5000" />
  <Navbar />
  <NuxtPage />
  <Footer />
  <Up />
  <script src="../path/to/flowbite/dist/flowbite.min.js"></script>
</template>

<script setup>
  const base = 'http://localhost:1338' 
  const api = await $fetch(`${base}/api/config?populate=*`)
  const config = api.data

  useHead({
    title: config.title,
    meta: [
      { name: 'description', content: config.desc },
      { name: 'keywords', content: config.keywords },
    ],
    link: [
      { rel: 'icon', type: 'image/x-icon', href: base+config.favicon.url },
    ],
    bodyAttrs: {
      class: 'container mx-auto'
    },
  })
</script>