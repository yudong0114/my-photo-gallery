<template>
  <img :src="photoUrl" alt="" class="photo">
</template>

<script>
export default {
  name: 'PhotoAtom',
  props: {
    photoUrl: {
      type: String,
      required: true
    }
  }
}
</script>

<style lang="scss" scoped>
.photo {
  aspect-ratio: 1 / 1;
  object-fit: cover;
  transition: 1s all;
  &:hover {
    transform: scale(1.2, 1.2);
    transition: 1s all;
  }
}
</style>
