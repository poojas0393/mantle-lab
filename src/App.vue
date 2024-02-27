<template>
  <main class="flex justify-start flex-col gap-14 px-5 pt-20 pb-10">
    <header>
      <h1 class="text-5xl font-medium text-left">Tasks Manager</h1>
    </header>
    <TaskList />
  </main>
</template>

<script setup>
import TaskList from './components/TaskList.vue';

</script>

<style>
  
  .text-5xl {color: #5f5f62;}
  * {
    font-family: 'Poppins', 'Arial Narrow', Arial, sans-serif;
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    list-style: none;
  }

  body {
    background-color: var(--body-bg);
    color: var(--body-color);
    min-height: 100vh;
    height: 100%;
    position: relative;
  }


</style>
