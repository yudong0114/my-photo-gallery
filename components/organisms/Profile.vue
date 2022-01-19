<template>
  <section id="profile" class="profile">
    <div class="profile__inner">
      <h1 class="profile__title">Profile</h1>
      <div class="profile__photo"><img src="@/static/image/img_profile_01.png" alt="プロフィール画像"></div>
      <dl class="profile__about">
        <div class="profile__group">
          <dt class="profile__key">name</dt>
          <dd class="profile__val">Yudong</dd>
        </div>
        <div class="profile__group">
          <dt class="profile__key">work</dt>
          <dd class="profile__val">Frontend Engineer</dd>
        </div>
        <div class="profile__group">
          <dt class="profile__key">hobby</dt>
          <dd class="profile__val">Take a picture</dd>
        </div>
      </dl>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ProfileOrganisms',
}
</script>

<style lang="scss" scoped>
.profile {
  padding: 50px 0;
  background: $bg-color-gray;
  &__title {
    font-size: 3.0rem;
    text-align: center;
  }
  &__photo {
    width: 150px;
    height: 150px;
    margin: 10px auto;
  }
  &__about {
    margin: 10px 0;
    font-size: 2.0rem;
    @include mobile {
      font-size: 1.4rem;
    }
  }
  &__group {
    display: flex;
    justify-content: space-between;
    margin: auto 20%;
  }
}
</style>


