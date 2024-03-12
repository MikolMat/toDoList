<script setup>
  import {ref, onMounted, computed, watch} from 'vue';

  const todos = ref([]);
  const name = ref('');

  const input_content = ref('');
  const input_category = ref(null);

  const todosSort = computed(() => todos.value.sort((a,b) => {
    return b.createdAt - a.createdAt;
  }))

  const addTodo = () => {};

</script>

<template>

  <main class="app">

    <section class="greeting">
        <h2 class="title">
          What's up, <input type="text" placeholder="Your Name" v-model="name">
        </h2>
    </section>

    <section class="create-todo">
      <h3>CREATE A TODO</h3>
      <form @submit.prevent="addTodo">
      
        <h4>What's on your to do list?</h4>
        <input type="text" placeholder="cos tam" v-model="input_content" />
        
        <h4>Pick a category</h4>
        <div class="options">

          <label>
            <input type="radio" name="category" value="business" v-model="input_category" />
          </label>

        </div>
      </form>
    </section>

  </main>

</template>
