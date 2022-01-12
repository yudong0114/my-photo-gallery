<template>
  <div class="photo-card">
    <Photo :photo-url="photoUrl" />
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
    photoUrl: {
      type: String,
      required: true
    }
  }
}
</script>
