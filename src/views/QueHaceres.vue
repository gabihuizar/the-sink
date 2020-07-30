<template>
  <div class="quehaceres">
    <QueHacer todo="ponte hacer que hacer" />
  </div>
</template>
<script>
// @ is an alias to /src
import QueHacer from '@/components/QueHacer.vue'

export default {
  name: 'QueHaceres',
  components: {
    QueHacer
  }
}
</script>
