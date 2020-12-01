<template>
  <Layout>
    <h1>Hi, I'm Aaron</h1>

    <p>
      I'm a front end developer based in Surrey.
    </p>
    <p>
      This is my new portfolio and personal site. <span class="sub">(It's very much a work in progress)</span>
    </p>

    <section>
      <h2>Recent posts</h2>
      <article v-for="edge in $page.posts.edges" :key="edge.node.id">
        <h3><g-link :to="edge.node.path">{{ edge.node.title }}</g-link></h3>
      </article>
    </section>
    
  </Layout>
</template>

<page-query>
  query {
    posts: allPost(sortBy: "date", order: DESC) {
      edges {
        node {
          id
          title
          path
        }
      }
    }
  }
</page-query>

<script>
export default {
  metaInfo: {
    title: 'Aaron Baker - Front End Developer'
  }
}
</script>

<style>
.sub {
  font-size: 0.7em;
}
</style>
