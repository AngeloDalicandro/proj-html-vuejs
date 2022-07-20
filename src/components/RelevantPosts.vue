<template>
    <section>
        <div class="container">
            <div class="popular">
                <h3>POPULAR POSTS</h3>

                <ul>
                    <li v-for="post, index in popularPosts" :key="`popular-post${index}`" >
                        <div>
                            <img :src="post.imagePreview" :alt="`Image for Article: ${post.title}`">

                            <div class="card-details">
                                <h2> {{ post.title }} </h2>
                                <div class="date"> {{ post.date }} </div>
                            </div>
                        </div>
                    </li>
                </ul>
            </div>

            <div class="recent"> 

                <h3> RECENT POSTS</h3>
                  <ul>
                    <li v-for="post, index in recentPosts" :key="`recent-post${index}`" >
                        <div>
                            <img :src="post.imagePreview" :alt="`Image for Article: ${post.title}`">

                            <div class="card-details">
                                <h2> {{ post.title }} </h2>
                                <div class="date"> {{ post.date }} </div>
                            </div>
                        </div>
                    </li>
                </ul>
            </div>

            
            <div class="featured">
                <h3>FEATURED POSTS</h3>
                
                <div class="post">
                        <img :src="featuredPost.image" :alt="`Image for the article: ${featuredPost.title}`">

                        <div class="post-info">
                            <div v-for="category, index in featuredPost.categories" :key="index" class="category"> {{ category.toUpperCase() }} </div>

                            <h2 class="title"> {{ featuredPost.title }} </h2>

                            <div class="text-preview"> {{ featuredPost.textPreview }} </div>
                        </div>
                </div>

                <h3>FEATURED AUTHOR</h3>

                <div class="author">
                    <img :src="featuredAuthor.avatar" :alt="featuredAuthor.name">

                    <div class="info">
                        <div> {{  featuredAuthor.name }} </div>

                        <div> {{ featuredAuthor.details }} </div>
                    </div>
                </div>
            </div>
           
           
        </div>
    </section>
</template>

<script>


export default {
    name: "RelevantPosts",
    props: {
        posts: Array
    },
    data() {
        return {
            popularPosts: this.getPopularPosts(),
            recentPosts: this.getRecentPosts(),
            featuredPost: this.getFeaturedPost(),
            featuredAuthor: {
                name: "John Doe",
                details: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Lorem ipsum dolor sit amet.",
                avatar: require("../assets/images/avatar.jpg")
            }
        }
    },
    methods: {
        getPopularPosts() {
            let popular = [];

            this.posts.forEach((post) => {
                if(post.popular) {
                    popular.push(post);
                }
            });

            return popular;
        },
        getRecentPosts() {
            let popular = [];

            this.posts.forEach((post) => {
                if(post.recent) {
                    popular.push(post);
                }
            });

            return popular;
        },
        getFeaturedPost() {
            let featuredPost = {};

            this.posts.forEach((post) => {
                if(post.feaured) {
                    featuredPost = post;
                }
            });

            return featuredPost;
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../styles/variables";

    section {
        padding: 4rem 0;
        
        .container {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 1rem;

            ul {
                list-style-type: none;
                
                li {
                    padding: 1rem 0;

                    div {
                        display: flex;
                        font-size: 0.75rem;

                        img {
                            width: 4rem;
                            margin-right: 00.5rem;
                        }

                        .card-details {
                            padding: 0.25rem;
                            display: flex;
                            flex-direction: column;
                            gap: 0.25rem;

                            h2 {
                                font-weight: 500;
                            }
                            .date {
                                color: $a-grey;
                            }
                        }
                    }
                }
            }

            .featured {
                
                .post {
                    margin: 2rem 0; 
                }
                .author {
                    margin-top: 1rem;
                    display: flex;

                    img {
                        width: 8rem;
                    }

                    .info {
                        padding: 0.5rem 1rem;

                        div:first-child  {
                            font-weight: 800;
                            font-size: 1.25rem;
                            margin-bottom: 0.5rem;
                        }

                        div:last-child {
                            color: $a-grey;
                        }
                    }
                }
            }
        }   
    }
</style>