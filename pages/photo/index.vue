<template>
  <main>
    <h1>一覧</h1>
    <ul>
      <li v-for="content in contents" :key="content.id">
        <nuxt-link :to="`/photo/${content.id}`">
          {{ content.title }}
        </nuxt-link>
      </li>
    </ul>
  </main>
</template>

<script>
import axios from 'axios';
export default {
  name: 'PhotoIndexPage',
  async asyncData() {
    const { data } = await axios.get(
      `${process.env.MICROCMS_API_URL}`,
      {
        headers: { 'X-MICROCMS-API-KEY': `${process.env.MICROCMS_API_KEY}` }
      }
    )
    return data
  }
}
</script>
