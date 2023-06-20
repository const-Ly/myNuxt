<template>
  <div>
    <h1>我是首页</h1>
    <h2>{{ title }}</h2>
    <NuxtLink to="/test">Test</NuxtLink>
    <button @click="toggleModal">isModalOpen</button>
  </div>
</template>

<script setup>
import { ref } from "vue"
const title = ref('我是标题')
let isModalOpen = true

function toggleModal() {
  isModalOpen = !isModalOpen
}

// all your favourites, fully typed
useHead({
  title: 'Hello World',
  titleTemplate: (title) => `${title} | MySite`,
  // class API support
  bodyAttrs: { class: { overflow: () => isModalOpen } },
  meta: [
    { name: 'description', content: 'Hello World' },
    { name: 'keywords', content: 'Hello World keywords' },
    { name: 'apple-mobile-web-app-title', content: 'Omega' },
  ],
  script: [{ src: 'https://example.com/script.js', async: true }],
  link: [{
    rel: 'stylesheet',
    href: 'https://img.cacheserv.com/website/www-omega/en/prev4.css'
  }],
})


</script>