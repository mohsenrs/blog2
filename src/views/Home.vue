<template>
  <div class="home">
    <h1>Home</h1>
    <div v-if="error">{{ error }}</div>
    <div v-if="posts.length">
      <PostList v-if="showPosts" :posts="posts" />
    </div>
    <div v-else>
      <small>Loading data...</small>
    </div>
    <br />
    <button @click="toggleShow">toggle</button>
    <button @click="posts.shift()">delete a post</button>
  </div>
</template>

<script>
import { ref } from "vue";
import PostList from "../components/PostList";
import getPosts from "../composables/getPosts";

export default {
  name: "Home",
  components: { PostList },
  setup() {
    const { posts, error, load } = getPosts();
    load();

    const showPosts = ref(true);
    const toggleShow = () => {
      showPosts.value = !showPosts.value;
    };

    return { posts, showPosts, toggleShow, error };
  },
};
</script>
