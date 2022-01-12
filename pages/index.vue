<template>
  <main>
    <h1>TOP</h1>
    <ul>
      <li v-for="content in contents" :key="content.id">
        <PhotoCard :photo-url="content.photo.url" />
      </li>
    </ul>
  </main>
</template>

<script>
import axios from 'axios';
import PhotoCard from '@/components/organisms/PhotoCard.vue';

export default {
  name: 'IndexPage',
  components: {
    PhotoCard,
  },
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
