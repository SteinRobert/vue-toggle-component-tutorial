<template>
  <div>
    <app-toggle :active.sync="toggleActive" label="Wifi"></app-toggle>
  </div>
</template>

<script>
  import Toggle from './Toggle'

  export default {
    name: 'App',
    components: {
      'AppToggle': Toggle
    },
    data () {
      return {
        toggleActive: true
      }
    }
  }
</script>