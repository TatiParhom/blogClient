<template>
  <NuxtLoadingIndicator throttle="0" duration="5000" />
  <Navbar />
  <NuxtPage />
  <Footer />
  <Upp />
</template>

<script>
const base = 'http://http://panel.e436b3cc88eb.vps.myjino.ru'
const api = await $fetch(`${base}/api/config?populate=*`)
const config = api.data

useHead({
  title: config.title,
  meta: [
    { name: 'description', content: config.desc },
    { name: 'keywords', content: config.keywords },
  ],
  link: [
    { rel: 'icon', type: 'image/x-icon', href: base + config.favicon.url },

  ],
  bodyAttrs: {
    class: 'container mx-auto'
  },
})
</script>