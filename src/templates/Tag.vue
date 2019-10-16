<template>
  <div>{{ $page.tag.title }}</div>
</template>

<page-query>
query ($id: ID){
  tag(id: $id) {
    title
    belongsTo {
      edges {
        node {
          ... on Post {
            title
          }
        }
      }
    }
  }
}
</page-query>