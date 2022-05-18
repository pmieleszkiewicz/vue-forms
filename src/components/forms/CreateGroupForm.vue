<script setup>
import BasicInfoForm from './partials/BasicInfoForm.vue'
import AdditionalInfoForm from './partials/AdditionalInfoForm.vue'
import {ref} from "vue";

const firstName = ref('');
const lastName = ref('');
const age = ref(0);
const nickname = ref('');

const changeFirstName = (value) => {
  firstName.value = value;
}

const changeLastName = (value) => {
  lastName.value = value;
}

const changeAge = (value) => {
  age.value = value;
}

const changeNickname = (value) => {
  nickname.value = value;
}

const submitForm = () => {
  console.log('Submitting full form with data:', {
    'firstName': firstName.value,
    'lastName': lastName.value,
    'age': age.value,
    'nickname': nickname.value,
  })
}
</script>

<template>
  <div class="create-form">
    <h1>CreateGroupForm</h1>
    <code>
      <p>firstName: {{ firstName }}</p>
      <p>lastName: {{ lastName }}</p>
      <p>age: {{ age }}</p>
      <p>nickname: {{ nickname }}</p>
    </code>
    <BasicInfoForm
        :first-name="firstName"
        :last-name="lastName"
        @first-name-changed="changeFirstName"
        @last-name-changed="changeLastName"
    >
    </BasicInfoForm>
    <AdditionalInfoForm
        :age="age"
        :nickname="nickname"
        @age-changed="changeAge"
        @nickname-changed="changeNickname"
    ></AdditionalInfoForm>
    <button @click="submitForm">Create</button>
  </div>
</template>

<style>
</style>
