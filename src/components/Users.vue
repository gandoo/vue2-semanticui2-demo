
<template>
  <list :error="error" :loading="loading" :listdata="listdata"></list>
</template>

<script>
import { listLoader, listGetter } from '../utils'
import List from './List'

export default {
  name: 'users',
  components: { List },
  data () {
    return { loading: true, error: null }
  },
  computed: {
    listdata () {
      return listGetter.call(this, 'getUsers')
    }
  },
  created () {
    listLoader.call(this, 'userlist')
  }
}
</script>

<style scoped>
</style>
