<template>
  <div class="hello">
    <div>{{ msg }}</div>
    <button @click="increment">
      Count is: 
    </button>
    <div>{{ state.n }}</div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { reactive, ref } from "vue";

export default defineComponent({
  name: "HelloWorld",
  props: {
    msg: String,
  },
  setup(props) {
    const state = reactive({
      n: 0
    });
    console.log(props);
    
    function increment() {
      state.n++;
    }

    return { state, increment };
  },

});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
