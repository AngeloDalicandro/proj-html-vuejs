<template>
    <section>
        <div class="container">
            <div @click="slideDown()" class="icon">
                <font-awesome-icon icon="fa-solid fa-angle-left" />
            </div>
            
            <div class="btn" v-for="activeElement, index in thisActiveElements" :key="index">
                {{ activeElement.toUpperCase() }}
            </div>

            <div @click="slideUp()" class="icon">
                <font-awesome-icon icon="fa-solid fa-angle-right" />
            </div>
        </div>
    </section>
</template>

<script>

export default {
    name: "CategoriesSection",
    props: {
        categories: Array
    },
    data() {
        return {
            activeElements: [0, 1, 2, 3, 4, 5]
        }
    },
    computed: {
        thisActiveElements() {
            let activeElements = [];

            this.activeElements.forEach((index) => {
                activeElements.push(this.categories[index])
            });

            return activeElements;
        }
    },
    methods: {
        slideUp() {
            let selectedActiveElements = [];

            this.activeElements.forEach((number) => {
                if(number != this.categories.length -1) {
                    selectedActiveElements.push(number + 1);
                } else {
                    selectedActiveElements.push(0);
                }
            });

            this.activeElements.splice(0, 6);
            this.activeElements = [...selectedActiveElements];
        },

        slideDown() {
            let selectedActiveElements = [];

            this.activeElements.forEach((number) => {
                if( number != 0) {
                    selectedActiveElements.push(number -1 );
                } else {
                    selectedActiveElements.push(this.categories.length -1);
                }
            });
            
            this.activeElements.splice(0, 6);
            this.activeElements = [...selectedActiveElements];
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../styles/variables.scss";

    section {
        background-color: $main-color;
        
        .container {
            font-size: 1.25rem;
            height: 8rem;
            display: grid;
            grid-template-columns: 1fr repeat(6, 4fr) 1fr;
            align-items: center;
            gap: 2rem;

            .icon {
                color: $btn-bgc;
                cursor: pointer;

                &:last-of-type {
                    text-align: right;
                }
            }

            .btn {
                text-align: center;
                color: $white;
                background-color: $btn-bgc;
                padding: 1rem 0;
                cursor: pointer;

                &:hover {
                    border: 3px solid $main-color;
                }
            }
        }

    }

</style>