<template>
  <div class="col-span-4 sm:col-span-12 mt-6 relative mb-6">
    <div v-for="post in posts" :key="post.slug">
      <Card :title="post.title" :content="post.content" :metadata="post.metadata" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Cards',
  props: ['posts']
}
</script>