<template>
    <header>

        <div class="header-top">
            <div class="container">

                <h1>Everything about Lifestyle, Travel and Gadgets!</h1>

                <ul>
                    <li v-for="topLink, index in topLinks" :key="`toplink${index}`">
                        <a :href="topLink.link"> {{ topLink.text.toUpperCase() }} </a>
                    </li>
                </ul>

            </div>
        </div>

        <div class="header-logo">
            <div class="container">
                <img :src="logoUrl" alt="Logo">
            </div>
        </div>

        <div class="header-nav">
            <div class="container">
                <nav>
                    <ul>
                        <li v-for="navLink, index in navLinks" :key="`navLink${index}`" :class="{ 'active' : index === activeElement}">
                            <a @click="setActiveElement(index)" :href="navLink.link"> {{ navLink.text.toUpperCase() }} </a>
                        </li>
                    </ul>
                </nav>

                <font-awesome-icon icon="fa-solid fa-magnifying-glass" />
            </div>
        </div>
    </header>
</template>

<script>
import topLinks from "../assets/header-top-links.json";
import navLinks from "../assets/nav-links.json";

export default {
    name: "BlogHeader",
    data() {
        return {
            topLinks: topLinks,
            navLinks: navLinks,
            logoUrl: require("../assets/images/logo-default-slim.png"),
            activeElement: 0
        }
    },
    methods: {
        setActiveElement(index) {
            this.activeElement = index;
        }
    }
}
</script>

<style lang="scss" scoped>
    @import "../styles/variables.scss";

    header {

        .header-top {
            background-color: $main-color;
            color: $white;

            .container {
                height: 3.5rem;
                display: flex;
                align-items: center;
                gap: 1rem;

                h1 {
                    font-size: 0.75rem;
                    font-weight: 500;
                }

                ul {
                    list-style-type: none;
                    display: flex;
                    gap: 1rem;
                    font-size: 1rem;

                    li {
                        font-size: 0.75rem;
                        font-weight: 500;

                        a {
                            text-decoration: none;
                            color: inherit;
                        }
                    }
                }
            }
        }

        .header-logo {
            border-bottom: 2px solid $light-grey;
            
            .container {
                height: 8rem;
                display: flex;
                align-items: center;

                img {
                    width: 7.5rem;
                }
            }
        }

        .header-nav {

            .container {
                height: 4rem;
                display: flex;
                justify-content: space-between;
                align-items: center;

                ul {
                    list-style-type: none;
                    display: flex;
                    gap: 2rem;
                         
                    li {
                        font-weight: 800;
                        color: $nav-text;

                        &.active {
                            color: $main-color;
                        }

                        a {
                            text-decoration: none;
                            color: inherit;
                        }
                    }
                }
            }
        }
    }
</style>
