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
      <li v-for="(item, index) in subjects" :key="index">
        {{ item.content }}
        <button @click="deleteSubject(index)">Delete</button>
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

    function deleteSubject(index) {
      console.log("Delete....");
      subjects.value.splice(index, 1);
    }

    // expose the state to the template
    return {
      newSubject,
      addNewSubject,
      subjects,
      deleteSubject
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
