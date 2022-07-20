<template>
  <div id="app">
    <BlogHeader />

    <main>
      <TopSection :posts="blogPosts" />

      <RelevantPosts :posts="blogPosts" />

      <CategoriesSection :categories="categories" />

      <section class="articles-and-stuff">
        <div class="container">
          <ArticlesList :posts="blogPosts" />
        
          <RightColumn />
        </div> 
      </section>
    </main>

    <footer>
      <FooterTop :categories="categories" />

      <FooterBot  />
    </footer>
  </div>
</template>

<script>

import BlogHeader from "./components/BlogHeader.vue";
import TopSection from "./components/TopSection.vue";
import RelevantPosts from "./components/RelevantPosts.vue";
import CategoriesSection from "./components/CategoriesSection.vue";
import ArticlesList from "./components/ArticlesList.vue";
import RightColumn from "./components/RightColumn.vue";
import FooterTop from "./components/FooterTop.vue";
import FooterBot from "./components/FooterBot.vue"

export default {
  name: 'App',
  components: {
    BlogHeader,
    TopSection,
    RelevantPosts,
    CategoriesSection,
    ArticlesList,
    RightColumn,
    FooterTop,
    FooterBot
  },
  data() {
    return {
      blogPosts: [
        {
          title: "How To Make Better Concert Pictures in 30 Seconds",
          categories: [
            "photography"
          ],
          image: require("./assets/images/blog-46.jpg"),
          textPreview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
          date: "january 12, 2019",
          author: {
            name: "John Doe",
            details: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            avatar: "../assets/images/avatar.jpg"
          },
          commentsNumber: "12 Comments",
          imgTop: true,
          popular: false,
          recent: false,
          feaured: false,
          listed: false
        },
        {
          title: "Gadgets To Make Your Smartphone Even Smarter",
          categories: [
            "gadgets"
          ],
          image: require("./assets/images/blog-47.jpg"),
          textPreview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
          date: "january 12, 2019",
          author: {
            name: "John Doe",
            details: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            avatar: "./assets/images/avatar.jpg"
          },
          commentsNumber: "12 Comments",
          imgTop: true,
          popular: false,
          recent: false,
          feaured: false,
          listed: false
        },
        {
          title: "20 Top-Rated Tourist Attractions in Manhattan",
          categories: [
            "travel"
          ],
          image: require("./assets/images/blog-48.jpg"),
          textPreview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
          date: "january 12, 2019",
          author: {
            name: "John Doe",
            details: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            avatar: "../assets/images/avatar.jpg"
          },
          commentsNumber: "12 Comments",
          imgTop: true,
          popular: false,
          recent: false,
          feaured: false,
          listed: false
        },
        {
          title: "The Best Way to Ride a Motorcycle",
          categories: [
            "lifestyle"
          ],
          image: require("./assets/images/blog-49.jpg"),
          textPreview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
          date: "january 12, 2019",
          author: {
            name: "John Doe",
            details: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            avatar: "../assets/images/avatar.jpg"
          },
          commentsNumber: "12 Comments",
          imgTop: true,
          popular: false,
          recent: false,
          feaured: false,
          listed: false
        },
        {
          title: "5 Fun Things to Do at the Beach",
          categories: [
            "travel"
          ],
          image: require("./assets/images/blog-50.jpg"),
          textPreview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
          date: "january 12, 2019",
          author: {
            name: "John Doe",
            details: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            avatar: "../assets/images/avatar.jpg"
          },
          commentsNumber: "12 Comments",
          imgTop: true,
          popular: false,
          recent: false,
          feaured: false,
          listed: false
        },
        {
          title: "Amazingly Fresh Fruit And Herb Drinks For Summer",
          categories: [
            "recipes"
          ],
          image: require("./assets/images/blog-51.jpg"),
          textPreview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
          date: "january 12, 2019",
          author: {
            name: "John Doe",
            details: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            avatar: "../assets/images/avatar.jpg"
          },
          commentsNumber: "12 Comments",
          imgTop: true,
          popular: false,
          recent: false,
          feaured: false,
          listed: false
        },
        {
          title: "How to Make Friends as a Grown-Up",
          categories: [
            "recipes"
          ],
          image: require("./assets/images/blog-54.jpg"),
          textPreview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
          date: "january 12, 2019",
          author: {
            name: "John Doe",
            details: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            avatar: "../assets/images/avatar.jpg"
          },
          commentsNumber: "12 Comments",
          imgTop: false,
          popular: false,
          recent: false,
          feaured: false,
          listed: true
        },
        {
          title: "Simple Ways to Have a Pretty Face",
          categories: [
            "photography",
            "travel"
          ],
          image: require("./assets/images/blog-55 (1).jpg"),
          imagePreview: require("./assets/images/blog-55.jpg"),
          textPreview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
          date: "january 12, 2019",
          author: {
            name: "John Doe",
            details: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            avatar: "../assets/images/avatar.jpg"
          },
          commentsNumber: "12 Comments",
          imgTop: false,
          popular: true,
          recent: false,
          feaured: false,
          listed: true
        },
        {
          title: "Ranking the Greatest Players in Basketball",
          categories: [
            "sports", 
            "business"
          ],
          image: require("./assets/images/blog-56 (1).jpg"),
          imagePreview: require("./assets/images/blog-56.jpg"),
          textPreview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
          date: "january 12, 2019",
          author: {
            name: "John Doe",
            details: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            avatar: "../assets/images/avatar.jpg"
          },
          commentsNumber: "12 Comments",
          imgTop: false,
          popular: true,
          recent: false,
          feaured: false,
          listed: true
        },
        {
          title: "4 Ways to Look Cool in Glasses",
          categories: [
            "lifestyle"
          ],
          imagePreview: require("./assets/images/blog-57.jpg"),
          textPreview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
          date: "january 12, 2019",
          author: {
            name: "John Doe",
            details: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            avatar: "../assets/images/avatar.jpg"
          },
          commentsNumber: "12 Comments",
          imgTop: false,
          popular: true,
          recent: false,
          feaured: false,
          listed: false
        },
        {
          title: "Top Camper Trailer Towing Tips",
          categories: [
            "travel",
            "lifestyle"
          ],
          image: require("./assets/images/blog-58 (1).jpg"),
          imagePreview: require("./assets/images/blog-58.jpg"),
          textPreview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
          date: "january 12, 2019",
          author: {
            name: "John Doe",
            details: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            avatar: "../assets/images/avatar.jpg"
          },
          commentsNumber: "12 Comments",
          imgTop: false,
          popular: true,
          recent: false,
          feaured: false,
          listed: true
        },
        {
          title: "5 Lovely Walks in New York",
          categories: [
            "travel",
            "lifestyle"
          ],
          imagePreview: require("./assets/images/blog-59.jpg"),
          textPreview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
          date: "january 12, 2019",
          author: {
            name: "John Doe",
            details: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            avatar: "../assets/images/avatar.jpg"
          },
          commentsNumber: "12 Comments",
          imgTop: false,
          popular: true,
          recent: false,
          feaured: false,
          listed: false
        },
        {
          title: "Main Reasons to Stop Texting and Driving",
          categories: [
            "lifestyle"
          ],
          image: require("./assets/images/blog-65 (1).jpg"),
          imagePreview: require("./assets/images/blog-65.jpg"),
          textPreview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
          date: "january 12, 2019",
          author: {
            name: "John Doe",
            details: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            avatar: "../assets/images/avatar.jpg"
          },
          commentsNumber: "12 Comments",
          imgTop: false,
          popular: false,
          recent: true,
          feaured: false,
          listed: false
        },
        {
          title: "Tips To Help You Quicly Prepare Your Lunch",
          categories: [
            "lifestyle"
          ],
          image: require("./assets/images/blog-66.jpg"),
          imagePreview: require("./assets/images/blog-66 (1).jpg"),
          textPreview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
          date: "january 12, 2019",
          author: {
            name: "John Doe",
            details: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            avatar: "../assets/images/avatar.jpg"
          },
          commentsNumber: "12 Comments",
          imgTop: false,
          popular: false,
          recent: true,
          feaured: true,
          listed: false
        },
        {
          title: "Why Should I Buy a Smartwatch?",
          categories: [
            "lifestyle",
            "technology"
          ],
          image: require("./assets/images/blog-67 (1).jpg"),
          imagePreview: require("./assets/images/blog-67.jpg"),
          textPreview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
          date: "january 12, 2019",
          author: {
            name: "John Doe",
            details: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            avatar: "../assets/images/avatar.jpg"
          },
          commentsNumber: "12 Comments",
          imgTop: false,
          popular: false,
          recent: true,
          feaured: false,
          listed: false
        },
        {
          title: "The Best Augmented Reality Smartglasses",
          categories: [
            "technology"
          ],
          imagePreview: require("./assets/images/blog-68.jpg"),
          textPreview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
          date: "january 12, 2019",
          author: {
            name: "John Doe",
            details: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            avatar: "../assets/images/avatar.jpg"
          },
          commentsNumber: "12 Comments",
          imgTop: false,
          popular: false,
          recent: true,
          feaured: false,
          listed: false
        },
        {
          title: "12 Healthiest Foods to Eat for Breakfast",
          categories: [
            "recipes"
          ],
          imagePreview: require("./assets/images/blog-69.jpg"),
          textPreview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
          date: "january 12, 2019",
          author: {
            name: "John Doe",
            details: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            avatar: "../assets/images/avatar.jpg"
          },
          commentsNumber: "12 Comments",
          imgTop: false,
          popular: false,
          recent: true,
          feaured: false,
          listed: false
        },
        {
          title: "10 Best Travel Tips After 5 Years Traveling The World",
          categories: [
            "travel",
            "lifestyle"
          ],
          images: [
            require("./assets/images/blog-13.jpg"),
            require("./assets/images/blog-16.jpg"),
            require("./assets/images/blog-20.jpg"),
            require("./assets/images/blog-23.jpg"),
            require("./assets/images/blog-29.jpg"),
            require("./assets/images/blog-40.jpg")
          ],
          textPreview: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
          date: "january 12, 2019",
          author: {
            name: "John Doe",
            details: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            avatar: "../assets/images/avatar.jpg"
          },
          commentsNumber: "12 Comments",
          imgTop: false,
          popular: false,
          recent: false,
          feaured: false,
          listed: true
        }
      ],
      categories: ["gadgets", "photography", "lifestyle", "fashion", "recipes", "travel", "business", "architecture", "reviews", "sports", "videos", "technology", "design"]
    }
  }
}
</script>

<style lang="scss">
  @import "./styles/commons";

  .articles-and-stuff {
    padding-top: 2rem;
    .container {
      display: grid;
      grid-template-columns: 9fr 3fr;
      gap: 2rem;
    }
  }
</style>
