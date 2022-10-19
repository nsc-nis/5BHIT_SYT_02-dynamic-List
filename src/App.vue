<template>
  <div id="app">
    <h3>Example</h3>
    <form @submit.prevent="addNewSubject">
      <label>Enter new subject:</label>
      <input v-model="newSubject" />
      <button>Add subject</button>
    </form>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    const newSubject = ref("");

    function addNewSubject()
    {
      console.log("addNewSubject");
    }

    // expose the state to the template
    return {
      newSubject, addNewSubject
    };
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h3 {
  margin-bottom: 20px;
}
</style>
