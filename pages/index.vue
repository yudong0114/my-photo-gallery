<template>
  <main class="top">
    <PhotoList :photo-datas="contents" />
    <Profile />
  </main>
</template>

<script>
import axios from 'axios';
import PhotoList from '@/components/organisms/PhotoList.vue';
import Profile from '@/components/organisms/Profile.vue';

export default {
  name: 'IndexPage',
  components: {
    PhotoList,
    Profile,
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
  },
  head() {
    return {
      title: 'Yudong’s Photo Gallery',
    }
  }
}
</script>
