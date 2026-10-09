<script setup lang="ts">
definePageMeta({
  layout: 'login',
})

useSeoMeta({
  title: 'Lynk',
  description: 'Lynk, Connect Fast｜快速连结',
})
</script>

<template>
  <div class="flex flex-1 items-center justify-center px-6 py-16">
    <Login />
  </div>
</template>
