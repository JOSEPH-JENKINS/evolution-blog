<template>
  <div class="w-full">
    <div class="w-3/4 h-[35rem] mb-6">
      <img :src="metadata.thumbnail.url" alt="hey" class="w-full h-full object-cover">
    </div>
    <div class="w-full">
      <h1 class="font-bold text-lg capitalize mb-6">{{ title }}</h1>
      <div class="w-1/2 text-ellipsis">
        {{ htmlConvert(content) }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    title: String,
    content: String,
    metadata: Object
  },
  methods: {
    htmlConvert: (str) => {
      return String(str)
              .replace(/&/g, '&amp;')
              .replace(/"/g, '&quot;')
              .replace(/'/g, '&#39;')
              .replace(/</g, '&lt;')
              .replace(/>/g, '&gt;');
    }
  }
}
</script>