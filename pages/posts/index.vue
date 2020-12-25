<template>
  <div class="container">
    <div class="mt-3" :key="index" v-for="(post, index) in posts">
      <NuxtLink :to="`posts/${post.slug}`">
        <h1 class="text-xl font-semibold">{{ post.slug }}</h1>
      </NuxtLink>
      <h2>{{ post.title }}</h2>
      <summary>{{ post.content }}</summary>
    </div>
  </div>
</template>
<script>
export default {
  async asyncData(context) {
    const posts = await context.app.$http.$get("https://api.nuxtjs.dev/posts");

    return {
      posts,
    };
  },
};
</script>