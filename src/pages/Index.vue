<template>
  <Layout>
    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <g-image alt="Example image" src="~/favicon.png" width="135" />

    <h1>Hello, world!</h1>
    <div v-for="edge in $page.allPost.edges" :key="edge.node.id">
      <p>{{ edge.node.title }}</p>
      <p>{{ edge.node.content }}{</p>
      <g-link v-for="tag in edge.node.tags" :key="tag.id" :to="tag.path">{{ tag.title }}</g-link>

      <g-link :to="edge.node.path">read</g-link>
    </div>
    <p class="home-links">
      <a href="https://gridsome.org/docs/" target="_blank" rel="noopener">Gridsome Docs</a>
      <a href="https://github.com/gridsome/gridsome" target="_blank" rel="noopener">GitHub</a>
    </p>
  </Layout>
</template>
<page-query>
{
  allPost{
    edges {
      node {
        id
        title
        Author
        content
        tags{
          id
          title
          path
        }
        path
      }
    }
  }
 
}
</page-query>
<script>
export default {
  metaInfo: {
    title: "Hello, world!"
  }
};
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
