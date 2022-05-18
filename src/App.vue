<script setup>
import CreateGroupForm from './components/forms/CreateGroupForm.vue';
import EditGroupForm from './components/forms/EditGroupForm.vue';
import {ref} from "vue";

const mode = ref('create');

</script>

<template>
  <div class="app">
    <a href="#" @click="mode = 'create'">Create form</a>
    <a href="#" @click="mode = 'edit'" style="margin-left: 1rem;">Edit form</a>

    <div v-if="mode === 'create'">
      <CreateGroupForm />
    </div>
    <div v-else>
      <EditGroupForm />
    </div>
  </div>
</template>

<style>
</style>
