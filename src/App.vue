<template>
  <div> {{ countStore.count }} </div>
  <button @click="handleClick">Click</button>
</template>

<script>
import { createStore } from 'vuex'

const store = createStore({
  state () {
    return {
      countStore:{
        count: 100
      }
    }
  },
  mutations: {
    increment (state) {
      state.countStore.count++
    }
  }
})

export default {
  name: 'App',
  data() {
    return {
      countStore : store.state.countStore
    }
  },
  methods: {
    handleClick : function() {
      store.commit('increment');
    },
  }
}

</script>
