<template>
  <main>
    <h1>TOP</h1>
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
  name: 'IndexPage',
  async asyncData() {
    const { data } = await axios.get(
      `${process.env.MICROCMS_API_URL}`,
      {
        headers: {
          'X-MICROCMS-API-KEY': `${process.env.MICROCMS_API_KEY}`,
          'cache-control': 'no-cache'
        }
      }
    )
    return data
  }
}
</script>
