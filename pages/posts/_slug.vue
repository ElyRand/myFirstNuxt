<template>
  <section class="container mx-auto">
    <h1>{{ post.title }}</h1>
    <h2>{{ post.description }}</h2>
    <img :src="post.image" />
  </section>
</template>
<script>
export default {
  async asyncData({ params, redirect }) {
    const texts = await fetch("https://api.nuxtjs.dev/posts");
    if (texts.ok) {
      const thePost = await texts.json();

      const filtered = thePost.find(({ slug }) => {
        console.log(slug);
        console.log(params.slug);
        return slug === params.slug;
      });
      return {
        post: filtered,
      };
    }
  },
};
</script>