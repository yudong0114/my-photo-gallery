<template>
  <footer class="footer">
    <div class="footer__sns">
      <a href="https://twitter.com/yudong0114" target="_blank" rel="noopener noreferrer">Twitter</a>
    </div>
    <p class="footer__copyright">© 2022 Yudong’s Photo Gallery.</p>
  </footer>
</template>

<script>
export default {
  name: 'FooterOrganisms',
}
</script>

<style lang="scss" scoped>
.footer {
  text-align: center;
  &__sns {
    margin: 20px 0;
    font-size: 2.0rem;
  }
  &__copyright {
    margin: 10px 0;
  }
}
</style>
