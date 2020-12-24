<template>
  <div>
    <section
      :style="{
        backgroundImage: actualImage,
      }"
      class="hero flex items-center justify-center bg-cover bg-center bg-no-repeat relative"
    >
      <span
        class="absolute left-0 text-white bg-red-800"
        @click="
          currentIndex =
            currentIndex - 1 < 0 ? images.length - 1 : currentIndex - 1
        "
      >
        back
      </span>
      <span
        class="absolute right-0 text-white bg-red-800"
        @click="currentIndex = (currentIndex + 1) % images.length"
      >
        next
      </span>
      <ul class="absolute flex bottom-4 space-x-4">
        <li
          class="w-5 h-5 border-10 border-opacity-80 rounded-full"
          v-for="(image, index) in images"
          :class="{
            'bg-blue-800 border-gray-200': index == currentIndex,
            'bg-gray-300 border-gray-300': index != currentIndex,
          }"
          :key="index"
          @click="currentIndex = index"
        ></li>
      </ul>
    </section>
    <section class="h-screen bg-red-200"></section>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      images: [
        "https://www.asus.com/media/CAen/banners/u7qjrikyo7l2o4tz/u7qjrikyo7l2o4tz-0_0_desktop.jpg",
        "https://www.asus.com/media/CAen/banners/9hqzmajpyxkjbjoy/9hqzmajpyxkjbjoy-0_0_desktop.jpg",
        "https://www.asus.com/media/CAen/banners/ftbkospo8kesddn8/ftbkospo8kesddn8-0_0_desktop.jpg",
      ],
      currentIndex: 0,
    };
  },
  computed: {
    actualImage() {
      return `url(${this.images[this.currentIndex]})`;
    },
  },
  transition: "home",
};
</script>

<style scoped>
.hero {
  height: calc(100vh - 70px);
}
.home-enter-active,
.home-leave-active {
  transition: opacity 0.5s;
  transform: translateX(-10);
}
.home-enter,
.home-leave-active {
  opacity: 0;
  transform: translateX(-10);
}
</style>