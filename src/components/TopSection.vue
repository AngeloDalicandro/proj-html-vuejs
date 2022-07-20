<template>
    <section>
        <div class="container">
            <div v-for="post, index in topPosts" :key="index">
                <div class="post" v-if="post.imgTop">
                    <img :src="post.image" :alt="`Image for the article: ${post.title}`">

                    <div class="post-info">
                        <div v-for="category, index in post.categories" :key="index" class="category"> {{ category.toUpperCase() }} </div>

                        <h2 class="title"> {{ post.title }} </h2>

                        <div class="text-preview"> {{ post.textPreview }} </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>

export default {
    name: "TopSection",
    props: {
        posts: Array
    },
    data() {
        return {
            topPosts: this.getTopPosts()
        }
    },
    methods: {
        getTopPosts() {
            let topPosts = [];

            this.posts.forEach((post) => {
                if(post.imgTop) {
                    topPosts.push(post);
                }
            });

            return topPosts
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../styles/variables";

    section {
        background-color: $light-grey;

        .container {
            padding: 4rem 0;
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 2rem;
        }
    }
</style>