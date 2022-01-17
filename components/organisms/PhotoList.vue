<template>
  <section class="photoList">
    <PhotoCard
      v-for="photoData in photoDatas"
      :key="photoData.id"
      :photo-id="photoData.id"
      :photo-url="photoData.photo.url"
    />
  </section>
</template>

<script>
import PhotoCard from '@/components/molecules/PhotoCard.vue';

export default {
  name: 'PhotoListOrganisms',
  components: {
    PhotoCard,
  },
  props: {
    photoDatas: {
      type: Array,
      required: true
    }
  },
}
</script>

<style lang="scss" scoped>
.photoList {
  margin: 50px 10px;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  &:after {
    content:"";
    display: block;
    width: 30%;
    height: 0;
  }
}
</style>
