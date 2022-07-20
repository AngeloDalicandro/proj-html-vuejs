<template>
    <div class="footer-top">
        <div class="container">
            <div class="get-in-touch">Get in Touch</div>

            <div class="about">
                <h3>ABOUT THE BLOG</h3>

                <p v-for="about, index in aboutTheBlog" :key="index"> {{ about }} </p>
            
                <div>VIEW MORE <font-awesome-icon icon="fa-solid fa-angle-right" /></div>
            </div>

            <div class="recent-posts">
                <h3>RECENT POSTS</h3>

                <div class="post" v-for="recentPost, index in recentPosts" :key="`recentPost${index}`">
                    <img :src="recentPost.img" alt="Author pro-pic">

                    <div>
                        <div class="text"> {{ recentPost.text }} </div>
                        <div class="date"> {{ recentPost.date }}  </div>
                    </div>
                </div>
            </div>

            <div class="recent-comments">
                <h3>RECENT COMMENTS</h3>

                <div class="comment" v-for="recentComment, index in recentComments" :key="`recentComment${index}`">
                    <div>
                        <span><font-awesome-icon class="icon" icon="fa-solid fa-angle-right" /></span> <b>{{ recentComment.author }}</b> commented on <span>{{ recentComment.commentArgument }}</span>
                    </div>

                    <div class="date"> {{ recentComment.date }} </div>
                </div>
            </div>

            <div class="categories">
                <h3>CATEGORIES</h3>

                <div>
                    <div class="category" v-for="category, index in categories" :key="`category${index}`" > {{ category.toUpperCase() }} </div>
                </div>
                
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "FooterTot",
    props: {
        categories: Array
    },
    data() {
        return {
            aboutTheBlog: [
                "Lorem ipsum dolor sit amet consectetur adipisicing elit. Eos debitis et exercitationem sint consectetur minima, a omnis quis quaerat expedita ipsum reprehenderit.", 
                "Lorem ipsum dolor sit amet consectetur adipisicing elit. Eos debitis et exercitationem sint consectetur minima, a omnis quis quaerat expedita ipsum reprehenderit."
            ],
            recentPosts: [
                {
                    img: require("../assets/images/our-office-4-square.jpg"),
                    text: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                    date: "12:53 AM Dec 19th"
                },
                                {
                    img: require("../assets/images/our-office-5-square.jpg"),
                    text: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                    date: "12:53 AM Dec 19th"
                }
            ],
            recentComments: [
                {
                    author: "John Doe",
                    commentArgument: "lorem ipsum dolor sit amet.",
                    date: "12:55 AM Dec 19th"
                },
                {
                    author: "John Doe",
                    commentArgument: "lorem ipsum dolor sit amet.",
                    date: "12:55 AM Dec 19th"
                }
            ]
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../styles/variables.scss";

.footer-top {
    background-color: $btn-bgc;

        .container {
            position: relative;
            padding: 4rem 0 6rem 0;
            display: grid;
            grid-template-columns: 4fr 3fr 3fr 2fr;
            gap: 1rem;

            .date {
                color: $b-grey;
                font-size: 0.75rem;
            }

            .get-in-touch {
                position: absolute;
                top: -1rem;
                left: 0;
                transform: translate(0, -10%);
                background-color: $main-color;
                color: white;
                font-size: 1.5rem;
                padding: 1rem 1.5rem ;
            }

            h3 {
                color: white;
                font-size: 1rem;
            }

            .about {
                p {
                    margin: 1rem 0;
                    color: $b-grey;
                }

                div {
                    color: white;
                    display: flex;
                    align-items: center;
                    gap: 0.25rem;
                    font-size: 0.75rem;
                    font-weight: 800;
                }
            }

            .recent-posts {
                display: flex;
                flex-direction: column;
                gap: 1rem;

                .post {
                    display: flex;
                    align-items: center;
                    gap: 0.5rem;

                    img {
                        border-radius: 50%;
                        width: 5rem;
                    }

                    .text {
                        color: $a-grey;
                        margin-bottom: 0.5rem;
                    }
                }
            }

            .recent-comments {
                display: flex;
                flex-direction: column;
                gap: 1rem;

                .comment {
                    line-height: 1.5rem;
                    color: $a-grey;

                    span {
                        color: $main-color;
                        font-weight: 800;

                        .icon {
                            font-size: 0.75rem;
                            margin-right: 0.25rem;
                        }
                    }

                    b {
                        color: $white;
                    }
                }


            }

            .categories {
                
                div {
                    display: flex;
                    flex-wrap: wrap;
                    gap: 0.25rem;

                    .category {
                        font-size: 0.75rem;
                        background-color: black;
                        color: white;
                        padding: 0.5rem;
                        border-radius: 5px;
                    }
                }
            }
        }
    }
</style>