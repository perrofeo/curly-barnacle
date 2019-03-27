<template>
  <Layout>
    <div v-for="edge in $page.posts.edges" :key="edge.node.id">
      {{ edge.node.id }}
      {{ edge.node.title }}
    </div>    
  </Layout>
</template>

<page-query>
query Posts {
  posts: Posts {
    edges {
      node { 
        id
        title
      }
    }
  }
}
</page-query>