<template>
  <div>
    <h1>User Slug Detail</h1>
    <p>Slug : {{ id }}</p>
    <nuxt-link to="/users">Back</nuxt-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      id: this.$route.params.slug,
    }
  },
  // validate({ params }) {
  //   return params.slug === '1'
  // },
}
</script>

<style></style>
