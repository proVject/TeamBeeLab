<template>
  <section class="hero py-2.5 md:py-6 lg-py-12">
    <div class="main-container flex items-center justify-between gap-0 lg:gap-10 flex-col lg:flex-row">
      <!-- Text Content -->
      <div class="text-left max-w-[450px] flex-1 order-2 lg:order-1 -mt-4 md:mt-0">
        <h1 class="hidden md:inline">
          Hi ! It seems I`m <span class="text-primary">kindness</span>
        </h1>
        <h1 class="inline md:hidden">
          Hi ! It <br/> seems I`m <br/><span class="text-primary">kindness</span>
        </h1>
        <p class="mt-2 md:mt-4 text-text-secondary inter-font hero__subtitle">but who knows</p>
        <cat-button @click="onClickMore" class="mt-8 md:mt-9 min-w-[300px]">Let's meet &rarr;</cat-button>
      </div>

      <!-- Image Content -->
      <div class="flex flex-1 justify-center flex-1 order-1 lg:order-2">
        <img class="max-w-[205px] md:max-w-[280px] lg:max-w-[385px] w-full m-auto" src="/hero-large.svg" alt="cat hero">
      </div>
    </div>
  </section>
</template>

<script setup>
import CatButton from "../ui/CatButton.vue";

const onClickMore = () => {
  alert('Hello')
}
</script>

<style scoped>
.hero {
  background-image: url('/hero-bg.svg');
  background-position: center;
  width: 100%;
}
.hero__subtitle{
  font-size: 24px;
  line-height: 16px;
}
@media screen and (max-width: 48rem) {
  .hero {
    background-size: cover;
    background-repeat: no-repeat;
  }
  .hero__subtitle{
    font-size: 16px;
    line-height: 16px;
  }
}
</style>