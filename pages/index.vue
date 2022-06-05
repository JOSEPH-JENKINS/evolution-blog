<template>
  <main class="grid grid-cols-4 sm:grid-cols-12 px-5 sm:px-20 h-screen w-screen overflow-x-hidden">
    <Navbar />
    <div class="scrolling-text col-span-4 sm:col-span-12 mt-20 sm:mt-6 md:mt-16">
      <div class="scroll-text w-full relative matrix3d flex">
        <div class="textmoving animate-text-animation flex transition-all">
          <h1 class="font-bold text-6xl sm:text-[18rem] md:text-[18rem] whitespace-nowrap">Trending</h1>
          <span class="spacing">*</span>
        </div>
        <div class="textmoving animate-text-animation flex mr-[224px] transition-all">
          <h1 class="font-bold text-6xl sm:text-[18rem] md:text-[18rem] whitespace-nowrap">Trending</h1>
          <span class="spacing">*</span>
        </div>
      </div>
    </div>
    <Cards :posts="posts" />
  </main>
</template>

<script>
const cosmic = require('cosmicjs');
const cosmicApi = cosmic();
const bucket = cosmicApi.bucket({
  slug: "evolution-production",
  read_key: "VIfUiXsxZAfi9JoYjKzQn3MMo5L1rgFaJPvgOABVzgvFZ71OuM"
})

export default {
  name: 'IndexPage',
  async asyncData () {
    const data = await bucket.getObjects({
      query: {
        type: 'posts'
      },
      props: 'slug,title,content,metadata'
    })
    const posts = await data.objects;
    return {
      posts
    }
  }
}
</script>
