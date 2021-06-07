<template>
  <header>
    <h1>the Blog</h1>
    <nav>
      <router-link :to="{ name: 'Home' }">Home</router-link>
      <router-link :to="{ name: 'Create' }">Create</router-link>
    </nav>
  </header>
</template>

<script>
export default {};
</script>

<style>
header {
  display: flex;
  justify-content: space-between;
  margin: 0 auto;
  align-items: center;
  max-width: 1200px;
}
header a {
  text-decoration: none;
  color: #bbb;
  margin-left: 20px;
}
header a.router-link-active {
  color: #444;
  font-weight: bold;
}
</style>
