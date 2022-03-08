<template>
    <div class="container">
      <Header></Header>
      <Search></Search>
    </div>
</template>

<script>
import Header from '@/components/Header.vue'
import Search from '@/components/Search.vue'

export default {
  components: {
    Header,
    Search
  }
}
</script>
