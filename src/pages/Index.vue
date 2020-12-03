<template>
  <Layout>
    <div class="container">
      <h1 class="hero-title">
        Hi, I'm<br>Aaron 👋
      </h1>
      <p class="hero-subtitle">
        I'm a front end developer based in Surrey.
      </p>
      <section>
        <h2>Recent posts</h2>
        <article v-for="edge in $page.posts.edges" :key="edge.node.id">
          <h3><g-link :to="edge.node.path">{{ edge.node.title }}</g-link></h3>
        </article>
      </section>
    </div>
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

<style scoped lang="scss">
.sub {
  font-size: 0.7em;
}

.hero-title {
  font-size: clamp(2rem, 13rem, 18vw);
  line-height: 1;
  margin: 4rem 0 4rem;
}

.hero-subtitle {
  font-size: clamp(1.6rem, 3rem, 9vw);
  margin-bottom: 6rem;
}
</style>
