<template>
  <div class="blog">
    blog
    {{ $route.params.id }}
    <book></book>
  </div>
</template>

<script>
import book from '../components/book';


export default {
  name: 'blog',
  components: {
    book

    
  }

}
</script>
<style scoped lang="scss">

</style>