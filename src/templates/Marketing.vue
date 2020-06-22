<template>
  <BlogLayout>
    <div>
      <h1>Marketing {{$page.post.title}}</h1>
      <img :src="$page.post.featuredImage" alt="blog" />
      <div v-html="$page.post.body" />
    </div>
  </BlogLayout>
</template>

<page-query>
  query Post($path: String!) {
    post: post(path: $path) {
      title,
      body,
      featuredImage
    }
  }
</page-query>

<script>
export default {
  metaInfo() {
    return {
      title: this.$page.post.title
    }
  }
}
</script>

<style>

</style>