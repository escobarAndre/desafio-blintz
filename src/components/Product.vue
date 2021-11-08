<template>
  <div class="product border border-grey-100 w-auto h-24 mx-3 my-5 rounded flex md:h-40 md:mx-0 lg:mx-0 ">
    <div class="w-44 h-auto bg-black rounded-l">
      <img class="w-full h-full" :src="image" alt="">
    </div>
    <div class="justify-between w-5/6 text-left flex">
      <div class="px-3 py-1 md:py-5">
        <h2 class="font-black text-base md:text-3xl">{{ title }}</h2>
        <h4 class="text-sm md:text-xl font-extralight mb-2 md:mb-2">{{ subtitle }}</h4>
        <div>
          <button class="bg-green-custom px-2 md:px-4 py-1 md:py-2 rounded text-white text-xs md:text-sm font-extrabold ml-0 mr-3">SHARE</button>
          <button class="bg-white px-2 md:px-4 py-1 md:py-2 rounded text-indigo-900 border border-indigo-900 text-xs md:ext-sm font-extrabold">ARCHIVE</button>
        </div>
      </div>
      <div class="h-full py-14 hidden md:inline">
        <div class=" text-white font-bold text-2xl bg-opacity-50 bg-gray-200 rounded-full h-12 w-12 flex items-center justify-center xl:mx-0 lg:mx-5 md:mx-5">RS</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    subtitle: String,
    image: String
  }
}
</script>

<style scoped>
  .bg-green-custom{
    background-color: #33b544;
  }
</style>
