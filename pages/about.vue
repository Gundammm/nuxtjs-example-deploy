<template>
  <div>
      <h1>About Page</h1>
      <nuxt-link to="/">Back to home</nuxt-link>
      <nuxt-link to="/users">User List</nuxt-link>
  </div>
</template>

<script>
export default {
  middleware: 'auth',
  layout: 'admin',
}
</script>