<template>
  <section class="photolist">
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
.photolist {
  margin: 50px 0;
  display: flex;
  justify-content: space-around;
}
</style>
