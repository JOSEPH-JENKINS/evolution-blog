<template>
  <div class="absolute h-screen w-screen sm:w-1/2">
    <div class="relative h-screen w-screen">
      <div class="absolute h-screen bg-black w-screen sm:w-1/2 sm:right-0 px-8 -translate-x-5 hidden items-center">
        <div class="links w-full text-white">
          <div class="link mb-6">
            <h1 class="font-bold text-4xl">Home.</h1>
          </div>
          <div class="link mb-6">
            <h1 class="font-bold text-4xl">About.</h1>
          </div>
          <div class="link mb-6">
            <h1 class="font-bold text-4xl">Contact.</h1>
          </div>
        </div>
      </div>
      <div class="hamburger-btn h-8 w-20 bg-black absolute right-10 sm:right-40 top-3 cursor-pointer">
        <div class="flex flex-col justify-between w-full h-full py-3 px-5">
          <div class="line h-px w-full bg-white"></div>
          <div class="line h-px w-full bg-white"></div>
        </div>
      </div>
    </div>
  </div>
</template>