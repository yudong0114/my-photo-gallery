<template>
  <div class="photoDetail">
    <PageTitle :page-title="title" />
    <figure class="photoDetail__photoArea">
      <img :src="photo.url" :alt="photo.title" class="photoDetail__photoImg">
    </figure>
    <p class="photoDetail__description">{{ description }}</p>
    <dl class="photoDetail__about">
      <div class="photoDetail__group">
        <dt class="photoDetail__key">撮影日</dt>
        <dd class="photoDetail__val">{{ new Date(date).toLocaleDateString() }}</dd>
      </div>
      <div class="photoDetail__group">
        <dt class="photoDetail__key">撮影地</dt>
        <dd class="photoDetail__val">{{ area.area }}</dd>
      </div>
      <div class="photoDetail__group">
        <dt class="photoDetail__key">タグ</dt>
        <dd class="photoDetail__val">{{ tag.tag }}</dd>
      </div>
    </dl>
  </div>
</template>

<script>
import axios from 'axios';
import PageTitle from '@/components/atoms/PageTitle.vue';

export default {
  name: 'PhotoDetailPage',
  components: {
    PageTitle,
  },
  async asyncData({ params }) {
    const { data } = await axios.get(
      `${process.env.MICROCMS_API_URL}/${params.slug}`,
      {
        headers: {
          'X-MICROCMS-API-KEY': `${process.env.MICROCMS_API_KEY}`,
          'cache-control': 'no-cache'
        }
      }
    )
    return data;
  },
  head() {
    return {
      title: this.title,
      meta: [
        { hid: 'description', name: 'description', content: `${this.description} | Yudong’s Photo Gallery` },
      ]
    }
  },
}
</script>

<style lang="scss" scoped>
.photoDetail {
  &__description {
    padding: 10px 0;
    text-align: center;
    font-size: 2.0rem;
    @include mobile {
      font-size: 1.4rem;
    }
  }
  &__about {
    font-size: 2.0rem;
    @include mobile {
      font-size: 1.4rem;
    }
  }
  &__group {
    margin: 0 20%;
    display: flex;
    justify-content: space-between;
  }
}
</style>
