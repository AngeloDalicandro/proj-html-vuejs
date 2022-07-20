<template>
    <div class="footer-bot">
        <div class="container">
            <div class="logo">
                <img :src="logo.url" :alt="logo.alt">

                <div> &copy; Copyright 2020. All Rights Reserved.</div>
            </div>

            
            <ul>
                <li v-for="link, index in links" :key="index">
                    <font-awesome-icon class="icon" icon="fa-solid fa-angle-right" /> <a :href="link.link"> {{ link.text }} </a>
                </li>
            </ul>
            
        </div>
    </div>
</template>

<script>
export default {
    name: "FooterBot",
    data() {
        return {
            logo: {url: require("../assets/images/logo-footer.png"), alt: "Logo"},
            links: [
                {
                    link: "#",
                    text: "FAQ's"
                },
                {
                    link: "#",
                    text: "Sitemap"
                },
                {
                    link: "#",
                    text: "Contact Us"
                },
            ]
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../styles/variables.scss";

.footer-bot {
    background-color: $footer-bot-bgc;
    .container {
        height: 8rem;
        display: flex;
        color: $b-grey;
        justify-content: space-between;
        align-items: center;
        font-size: 1rem;
        
        .logo {
            display: flex;
            align-items: center;

            img {
                width: 5rem;
                margin-right: 3rem;
            }
        }

        ul {
            list-style-type: none;
            display: flex;
            gap: 1rem;

            li {
                

                a {
                    color: inherit;
                    text-decoration: none;
                }
            }
        }

    }
}
</style>