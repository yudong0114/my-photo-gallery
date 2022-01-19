<template>
  <div class="photoCard">
    <nuxt-link class="header__link" :to="`/photo/${photoId}`">
      <Photo :photo-url="photoUrl" />
    </nuxt-link>
  </div>
</template>

<script>
import Photo from '@/components/atoms/Photo.vue';

export default {
  name: 'PhotoCardOrganisms',
  components: {
    Photo,
  },
  props: {
    photoId: {
      type: String,
      required: true
    },
    photoUrl: {
      type: String,
      required: true
    }
  }
}
</script>

<style lang="scss" scoped>
.photoCard {
  width: 30%;
  height: 30%;
  margin-bottom: 20px;
  overflow: hidden;
  border: 2px solid $text-color-black;
}

</style>
