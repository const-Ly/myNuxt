<template>
  <div>
    <h1>我是Test页</h1>
    <h2>{{ title }}</h2>
    <button @click="goBack">返回</button>
  </div>
</template>

<script setup>
import { ref } from "vue"

const router = useRouter()

const title = ref('我是test的标题')

function goBack() {
  router.go(-1)
}

useHead({
  title: 'Hello Test',
  titleTemplate: (title) => `${title} | MySite`,
  meta: [
    { name: 'description', content: 'Hello Test' },
  ]
})

</script>