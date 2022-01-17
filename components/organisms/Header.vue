<template>
  <header class="header">
    <nuxt-link class="header__title" :to="`/`">Yudong’s Photo Gallery</nuxt-link>
    <ul class="header__list" role="list">
      <li class="header__item"><nuxt-link class="header__link" :to="`/#profile`">Profile</nuxt-link></li>
      <li class="header__item"><nuxt-link class="header__link" :to="`/photo/`">Photos</nuxt-link></li>
    </ul>
  </header>
</template>

<script>
export default {
  name: 'HeaderOrganisms',
}
</script>

<style lang="scss" scoped>
.header {
  margin: 0 10px;
  display: flex;
  justify-content: space-between;
  &__title {
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 2.0rem;
    font-weight: 700;
    @include mobile {
      font-size: 1.4rem;
    }
  }
  &__list {
    display: flex;
    padding: 0;
    font-size: 2.0rem;
    @include mobile {
      font-size: 1.4rem;
    }
  }
  &__item {
    margin: 0 10px;
  }
}
</style>


