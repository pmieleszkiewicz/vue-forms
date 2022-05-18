<script setup>
defineProps({
  firstName: {
    type: String,
    required: true
  },
  lastName: {
    type: String,
    required: true
  },
  allowSubmit: {
    type: Boolean,
    default: false,
  }
})
const emit = defineEmits(['first-name-changed', 'last-name-changed', 'form-submitted'])
</script>

<template>
  <div class="basic-info-form">
    <h2>Basic information</h2>
    <form>
      <div class="form-group">
        <label for="firstName">First name</label>
        <input type="text" name="firstName" id="firstName" v-model="firstName" @input="emit('first-name-changed', firstName)">
      </div>

      <div class="form-group">
        <label for="lastName">Last name</label>
        <input type="text" name="lastName" id="lastName" v-model="lastName" @input="emit('last-name-changed', lastName)">
      </div>

      <div v-if="allowSubmit">
        <button @click.prevent="emit('form-submitted')">Save</button>
      </div>
    </form>
  </div>
</template>

<style>
</style>
