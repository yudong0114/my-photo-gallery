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
  width: 30vw;
  height: 30vw;
  object-fit: cover;
  transition: 1s all;
  &:hover {
    transform: scale(1.2, 1.2);
    transition: 1s all;
  }
}
</style>
