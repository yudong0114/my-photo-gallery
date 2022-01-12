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
