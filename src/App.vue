<template>
  <div id="app">
    <h3>Example</h3>
    <form @submit.prevent="addNewSubject">
      <label>Enter new subject:</label>
      <input v-model="newSubject" />
      <button>Add subject</button>
    </form>
    <hr />
    <ul>
      <li v-for="item in subjects">
        {{ item.content }}
      </li>
    </ul>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    const newSubject = ref("");
    const subjects = ref([]);

    function addNewSubject() {
      //console.log("addNewSubject" + newSubject.value);
      subjects.value.push({
        content: newSubject.value
      });
      newSubject.value = " ";
      console.log(subjects.value);
    }

    // expose the state to the template
    return {
      newSubject,
      addNewSubject,
      subjects
    };
  }
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

hr {
  margin-top: 20px;
  margin-bottom: 20px;
}
</style>
