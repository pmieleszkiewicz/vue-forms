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

const submitBasicForm = () => {
  console.log('Submitting basic info form with data:', {
    'firstName': firstName.value,
    'lastName': lastName.value,
  })
}

const submitAdditionalForm = () => {
  console.log('Submitting additional info form with data:', {
    'age': age.value,
    'nickname': nickname.value,
  })
}
</script>

<template>
  <div class="edit-form">
    <h1>EditGroupForm</h1>
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
        @form-submitted="submitBasicForm"
        allow-submit
    >
    </BasicInfoForm>
    <AdditionalInfoForm
        :age="age"
        :nickname="nickname"
        @age-changed="changeAge"
        @nickname-changed="changeNickname"
        @form-submitted="submitAdditionalForm"
        allow-submit
    ></AdditionalInfoForm>
  </div>
</template>

<style>
</style>
