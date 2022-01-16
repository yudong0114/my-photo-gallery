<template>
  <h1 class="pageTitle">{{ pageTitle }}</h1>
</template>

<script>
export default {
  name: 'LogoAtom',
  props: {
    pageTitle: {
      type: String,
      required: true
    }
  }
}
</script>

<style lang="scss" scoped>
.pageTitle {
  text-align: center;
  border-bottom: 2px solid;
}
</style>
