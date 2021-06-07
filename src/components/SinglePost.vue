<template>
  <div class="single-post">
    <router-link :to="{ name: 'Details', params: { id: post.id } }">
      <h5>
        {{ post.title }}
      </h5>
    </router-link>
    <p>
      {{ snippet }}
    </p>
    <span v-for="tag in post.tags" :key="tag">#{{ tag }}</span>
  </div>
</template>

<script>
import { computed } from "vue";
export default {
  props: ["post"],
  setup(props) {
    const snippet = computed(() => {
      return props.post.body.substring(0, 100) + "....";
    });

    return { snippet };
  },
};
</script>

<style></style>
