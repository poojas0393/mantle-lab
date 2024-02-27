<template>
  <article class="block p-6 border rounded-lg shadow bg-gray-800 border-gray-500 min-h-[220px]">
    <div class="flex items-center justify-between mb-4">
      <div class="flex justify-end gap-1">
        <button class="inline-block text-gray-300 hover:bg-gray-600 focus:ring-4 focus:outline-none focus:ring-gray-500 rounded-lg text-sm p-1.5" @click="openModalFunction(props.id)">
          Edit
        </button>
        <button class="inline-block text-gray-300 hover:bg-[#c53333] hover:text-gray-100 focus:ring-4 focus:outline-none focus:ring-gray-500 rounded-lg text-sm p-1.5" @click="removeTask(props.id)">
          Delete
        </button>
      </div>
    </div>
    <h5 class="mb-3 text-lg font-medium text-gray-50 dark:text-white">{{ props.title }}</h5>
    <p class="text-md text-gray-200" >{{ props.text }}</p>
  </article>
</template>

<script setup>
  // imports
  import { useStore } from 'vuex';
  import { defineProps } from 'vue';
  
  const store = useStore();

  // pas props
  const props = defineProps({
    text: String,
    title: String,
    id: Number,
  });

  // open edit task modal
  const openModalFunction = (taskId) => {
    store.dispatch('openModalEditTask');
    store.dispatch('setSelectedTask', taskId);
  }

  // handel remove task
  const removeTask = (taskId) => {
    
    if(confirm("Do you really want to delete?")){
      store.commit('removeTask', taskId);
    }
  }
</script>