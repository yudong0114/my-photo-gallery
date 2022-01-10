<template>
  <main class="main">
    <h1 class="title">{{ title }}</h1>
    <p class="publishedAt">{{ publishedAt }}</p>
    <p class="photo">{{ photo }}</p>
    <p class="area">{{ area }}</p>
    <p class="date">{{ date }}</p>
    <p class="tag">{{ tag }}</p>
    <p class="description">{{ description }}</p>
    <p class="top">{{ top }}</p>
  </main>
</template>

<script>
import axios from 'axios'

export default {
  async asyncData({ params }) {
    const { data } = await axios.get(
      `${process.env.MICROCMS_API_URL}/${params.slug}`,
      {
        headers: { 'X-MICROCMS-API-KEY': `${process.env.MICROCMS_API_KEY}` }
      }
    )
    return data
  }
}
</script>
