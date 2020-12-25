<template>
  <nav class="bg-black">
    <div class="container mx-auto flex items-center h-full px-2">
      <NuxtLink to="/" class="text-white">Logo </NuxtLink>
      <div class="ml-auto space-x-2">
        <NuxtLink to="/" class="text-white">Home </NuxtLink>
        <NuxtLink to="/about" class="text-white">About </NuxtLink>
        <NuxtLink to="/posts" class="text-white">Posts </NuxtLink>
        <NuxtLink to="/" class="text-white">My story </NuxtLink>
      </div>
    </div>
  </nav>
</template>
<style lang="postcss">
nav {
  height: 70px;
}
</style>