<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld :msg="doneTodos" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import { computed } from 'vue'
import { mapGetters, useStore } from 'vuex'
// commit1
// commit2
// commit3
// commit6
export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  setup() {
    const store = useStore()
    const getters = mapGetters(['doneTodos','doneTodosCount'])

    const storeGetters = {}
    Object.keys(getters).forEach(item => {
      const func = getters[item].bind({ $store: store })
      storeGetters[item] = computed(func)
    })
    return {
      ...storeGetters
    }
  }
}
</script>
