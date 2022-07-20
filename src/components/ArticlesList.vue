<template>
    <div class="cards">
        <div v-for="post, index in listedPosts" :key="index">
            <img v-if="post.image" :src="post.image" :alt="`Image for article: ${post.title}`">
            <div class="collage" v-else>
                <img class="collage-item" v-for="image, index in post.images" :key="index" :src="image" alt="Random photos">
            </div>

            
            <div class="details">
                <div class="date">
                    <div class="day"> 12 </div>
                    <div class="month"> Jan </div>
                </div>

                <div class="card-details">
                    <div class="text">
                        <h2> {{ post.title }} </h2>

                        <p> {{ post.textPreview }} </p>
                    </div>

                    <div class="bottom-details">
                        <ul>
                            <li>
                                <font-awesome-icon class="icon" icon="fa-regular fa-user" /> By <a href="#"> {{ post.author.name }} </a>
                            </li>

                            <li>
                                <font-awesome-icon class="icon" icon="fa-regular fa-folder" /> <a href="#" v-for="category, index in post.categories" :key="index"> {{ capitalize(category) }}<span v-if="post.categories.length - 1 != index">,</span>  </a> 
                            </li>

                            <li>
                                <font-awesome-icon class="icon" icon="fa-regular fa-comments" /> <a href="#"> {{ post.comments }} Comments </a>
                            </li>
                        </ul>

                        <div class="btn">READ MORE</div>
                    </div>
                </div>
            </div>
        </div>

        <div class="boxes">
            <div class="box"><font-awesome-icon icon="fa-solid fa-angle-left" /></div>
            <div class="box active">1</div>
            <div class="box">2</div>
            <div class="box">3</div>
            <div class="box"><font-awesome-icon icon="fa-solid fa-angle-right" /></div>
        </div>
    </div>
</template>

<script>
export default {
    name: "ArtisclesList",
    data() {
        return {
            listedPosts: this.getListedPosts()
        }
    },
    props: {
        posts: Array
    },
    methods: {
        getListedPosts() {
            let listed = [];

            this.posts.forEach((post) => {
                if(post.listed) {
                    listed.push(post);
                }
            });

            return listed;
        },
        capitalize(string) {
            return string.charAt(0).toUpperCase() + string.slice(1);
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../styles/variables.scss";

.cards {
    img {
        padding-top: 2rem;
    }

    .collage {
        padding-top: 2rem;
        width: 100%;
        display: flex;
        flex-wrap: wrap;

        .collage-item {
            width: calc(100% / 3);
        }
    }


    .details {
        padding: 1.5rem 0;
        display: flex;
        gap: 1rem;

        .date {
            display: flex;
            flex-direction: column;

            .day {
                text-align: center;
                font-weight: 800;
                padding: 1rem 0.75rem;
                background-color: $light-grey;
                color: $btn-bgc;
            }

            .month {
                text-align: center;
                padding: 0.25rem 0.75rem;
                background-color: $btn-bgc;
                color: $light-grey;
            }
        }

        .card-details {
            display: flex;
            flex-direction: column;

            .text {
                margin-bottom: 1rem;

                h2 {
                    margin-bottom: 1rem; 
                }

                p {
                    color: $b-grey;
                }
            }

            .bottom-details {
                display: flex;
                justify-content: space-between; 
                align-items: center;
                padding: 1.5rem 0;
                border-bottom: 2px solid $light-grey;

                ul {
                    list-style-type: none;
                    display: flex;
                    gap: 0.75rem;
                    font-size: 0.9rem;

                    li {
                        color: $b-grey;

                        .icon {
                            margin-right: 0.25rem;
                        }

                        a {
                            text-decoration: none;
                            color: $main-color;

                            span {
                                color: $b-grey;
                            }
                        }
                    }
                }

                .btn {
                    border: 1px solid $b-grey;
                    color: $b-grey;
                    font-size: 0.75rem;
                    padding: 0.25rem 0.5rem;
                    border-radius: 0.25rem;
                    cursor: pointer;
                }
            }
        }

    }

    .boxes {
        margin-top: 1rem;
        margin-bottom: 4rem;
        color: $main-color;
        display: flex;
        flex-wrap: wrap;
        justify-content: flex-end;

        .box {
            width: 2rem;
            height: 2rem;
            line-height: 2rem;
            text-align: center;
            border: 1px solid $a-grey;
            cursor: pointer;+

            .active {
                color: $white;
                background-color: $main-color;            
            }
        }
    }
}
</style>