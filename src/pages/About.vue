<template>
  <Layout>
    <RichText :html="$page.allPageItem.edges[0].node.content"></RichText>
  </Layout>
</template>

<script>
import RichText from '../components/RichText';

export default {
  metaInfo: {
    title: 'Hello, world!'
  },
  components: {
    RichText
  }
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>

<page-query>
query IndexQuery {
  allPageItem(filter: { codename: { eq: "about" } }) {
    edges {
      node {
        title
        content
        slug
      }
    }
  }
}

</page-query>