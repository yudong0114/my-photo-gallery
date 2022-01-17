<template>
  <div class="photo">
    <PageTitle page-title="Photo - List" />
    <PhotoList :photo-datas="contents" />
  </div>
</template>

<script>
import axios from 'axios';
import PageTitle from '@/components/atoms/PageTitle.vue';
import PhotoList from '@/components/organisms/PhotoList.vue';

export default {
  name: 'PhotoIndexPage',
  components: {
    PageTitle,
    PhotoList,
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
      title: '一覧',
      meta: [
        { hid: 'description', name: 'description', content: '写真一覧 | Yudong’s Photo Gallery' },
      ]
    }
  }
}
</script>
