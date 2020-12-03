<template>
    <Layout>
        <article class="container">
            <h1>{{ $page.post.title }}</h1>
            <div v-html="$page.post.content" />
        </article>
    </Layout>
</template>

<page-query>
    query ($id: ID!) {
        post(id: $id) {
            title
            content
        }
    }
</page-query>

<script>
export default {
    metaInfo() {
        return {
            title: this.$page.post.title + ' | Aaron Baker',
        };
    }
}
</script>