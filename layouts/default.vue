<template>
	<div>
		<Header />
		<main>
			<nuxt />
		</main>
		<Footer />
	</div>
</template>
<script>
import Vue from 'vue';
import Header from '@/components/organisms/Header.vue';
import Footer from '@/components/organisms/Footer.vue';

export default Vue.extend({
  name: 'DefaultLayout',
  components: {
    Header,
    Footer,
  },
})
</script>
<style lang="scss" scoped>

</style>
