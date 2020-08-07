<template>
  <div>
    <span>count is {{count}}</span><br>
    <span>object.n is {{object.n}}</span><br>
    <button @click="add">Add 1</button>
  </div>
</template>

<script>
import { ref, reactive } from 'vue';
export default {
  setup() {
    const count = ref(0);
    const object = reactive({ n: 999 })
    setTimeout(() => {
      count.value += 100
      object.n += 1000
    }, 3000)
    return {
      count,
      object
    }
  },
  methods: {
    add() {
      this.count += 1
      this.object.n += 1
    }
  }
}
</script>
count