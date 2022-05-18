<script setup>
defineProps({
  age: {
    type: Number,
    required: true
  },
  nickname: {
    type: String,
    required: true
  },
  allowSubmit: {
    type: Boolean,
    default: false,
  }
})
const emit = defineEmits(['age-changed', 'nickname-changed', 'form-submitted'])
</script>

<template>
  <div class="additional-info-form">
    <h2>Additional information</h2>
    <form>
      <div class="form-group">
        <label for="age">Age</label>
        <input type="number" name="age" id="age" v-model="age" @input="emit('age-changed', age)">
      </div>

      <div class="form-group">
        <label for="nickname">Nickname</label>
        <input type="text" name="nickname" id="nickname" v-model="nickname" @input="emit('nickname-changed', nickname)">
      </div>

      <div v-if="allowSubmit">
        <button @click.prevent="emit('form-submitted')">Save</button>
      </div>
    </form>
  </div>
</template>

<style>
</style>
