<template>
  <div class="hello">
    {{states }}
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'HelloWorld',
  data () {
    return {
      states: {}
    }
  },
  created () {
    axios.get('http://roadtrippers.herokuapp.com/api/v1/states/ ')
      .then(response => {
        console.log(response)
        this.states = response.data
      })
      .catch(err => {
        console.log(err)
      })
  }
}
</script>
