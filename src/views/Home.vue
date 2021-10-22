<template>
  <v-container fill-height fluid mt-14>
    
    <v-row align="center" justify="center">
      <register/>
    </v-row>
  </v-container>
</template>

<script>
import Register from '../components/Register.vue'

export default {
  components: { Register },
  name: 'Home'
}
</script>