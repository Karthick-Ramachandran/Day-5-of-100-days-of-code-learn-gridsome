<template>
  <div class="container">
    <div v-html="$page.post.content" />
  </div>
</template>


<page-query>
   query ($path: String!) {
  post(path: $path) {
    id
    content
  }
}
</page-query>