<template>
  <div v-for="post in posts" :key="post.id" class="post-list">
    <SinglePost :post="post" />
  </div>
</template>

<script>
import SinglePost from "./SinglePost";
export default {
  components: { SinglePost },
  props: ["posts"],
};
</script>

<style></style>
