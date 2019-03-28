<template>
  <Layout>
    <div class="article">
      <h1>{{ $page.posts.title }}</h1>
      <span>{{ $page.posts.date }}</span>
      <g-image :src="$page.posts.image"/>
      <div class="content" v-html="$page.posts.content" />
    </div>
  </Layout>
</template>

<script>
export default {
  metaInfo () {
    return {
      title: this.$page.posts.title
    }
  }
}
</script>

<page-query>
  query Posts ($path: String!) {
    posts (path: $path) {
      title
      date (format: "D MMMM, YYYY")
      content
    }
  }
</page-query>