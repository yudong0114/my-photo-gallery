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
  width: 30vw;
  height: 30vw;
  overflow: hidden;
}
</style>
