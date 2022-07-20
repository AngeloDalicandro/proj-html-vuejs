<template>
    <div class="column">
        <section class="tweetter">
            <h3>LATEST FROM TWITTER</h3>

            <div class="tweet" v-for="tweet, index in tweets" :key="index">
                <font-awesome-icon class="icon" icon="fa-brands fa-twitter" />
                
                <div>
                    <p> {{ tweet.text }} </p>
                    <div class="date"> {{ tweet.date }} </div>
                </div>
            </div>
        </section>

        <section class="instagram">
            <h3>PHOTOS FROM INSTAGRAM</h3>

            <div class="ig">
                <img v-for="photo, index in instagramPhotos" :key="index" :src="photo" alt="Instagram photo">
            </div>
        </section>

        <section class="tags">
            <h3>TAGS</h3>

            <div class="tag">
                <div v-for="tag, index in tags" :key="`tag${index}`">
                    {{ tag.toUpperCase() }}
                </div>
            </div>
        </section>

        <section class="facebook">
            <h3>FIND US ON FACEBOOK</h3>
            <a href="#"> Okler Themes</a>
        </section>
    </div>
</template>

<script>
export default {
    name: "RightColumn",
    data() {
        return {
            tweets: [
                {
                text: "If you have any suggestion for the next updates, let us know.",
                date: "01:05 PM Sep 18th"
                },
                                {
                text: "We have just updated Porto Admin. Check the changelog for more information.",
                date: "01:04 PM Sep 18th"
                }
            ],
            instagramPhotos: [require("../assets/images/ig-1.jpg"),require("../assets/images/ig-2.jpg"),require("../assets/images/ig-3.jpg"),require("../assets/images/ig-4.jpg"),require("../assets/images/ig-5.jpg"),require("../assets/images/ig-6.jpg")],
            tags: ["design", "brands", "video", "business", "travel"]
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../styles/variables.scss";

    .column {
        padding-top: 2rem;

        .tweet {
            padding-top: 1.5rem;
            display: flex;
            font-size: 1.25rem;
            color: $b-grey;

            .icon {
                padding: 0 0.5rem;
                color: $btn-bgc;
            }

            .date {
                padding-top: 0.25rem;
                font-size: 1rem;
                color: $main-color;
            }
        }

        .instagram {
            padding-top: 4rem;

            .ig {
                padding-top: 1rem;
                display: flex;
                flex-wrap: wrap;

                img {
                    width: calc(100% / 3);
                }
            }
        }

        .tags {
            padding-top: 4rem;

            .tag {
                padding-top: 1rem;
                display: flex;
                flex-wrap: wrap;
                gap: 0.5rem;

                div {
                    font-size: 0.75rem;
                    color: $white;
                    background-color: $btn-bgc;
                    padding: 0.25rem 0.5rem;
                    border-radius: 0.75rem;
                }
            }
        }

        .facebook {
            padding-top: 6rem;

            a {
                display: inline-block;
                text-decoration: none;
                color: $main-color;
                margin-top: 1rem;
                height: 3rem;
                line-height: 3rem;
                padding-left: 1rem;
                border-left: 6px solid $light-grey;
            }
        }
    }
</style>