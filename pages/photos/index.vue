<template>
  <div class="container">
    <h1>Photos</h1>

    <div class="photos">
      <nuxt-link
        :to="`/photos/${photo.id}`"
        v-for="photo in photos"
        :key="photo.id"
        class="text-link"
      >
        <!-- <img :src="photo.download_url" alt="photo" class="photo-item" /> -->
        <div class="photo">
          <h2>{{ photo.id }}</h2>
          <p>{{ photo.author }}</p>
        </div></nuxt-link
      >
    </div>
    <nuxt-link to="/">Back to Home</nuxt-link>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const photos = await $axios.$get('/v2/list')
    return { photos }
  },
}
</script>

<style scoped>
.container {
  padding: 1em;
  /* width: 1220px; */
  margin: 0 auto;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: flex-start;
}
.photos {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  grid-template-rows: auto;
  grid-gap: 1em;
  /* text-align: center; */
}
.photo-item {
  width: 100%;
  height: 256px;
  object-fit: cover;
}
.photo {
  background-color: #e0eaf3;
  margin: 10px;
  padding: 30px;
}
.text-link {
  text-decoration: none;
}
</style>
