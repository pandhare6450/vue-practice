<!-- OtpField.vue -->
<template>
  <div>
    <input
      v-for="(digit, index) in otpDigits"
      :key="index"
      v-model="otp[index]"
      type="text"
      maxlength="1"
      @input="onInput(index)"
    />
  </div>
</template>

<script setup>
import { ref } from 'vue';

const otpDigits = Array.from({ length: 6 }, (_, index) => index); // Change the length as per your OTP length
const otp = Array(6).fill('');

const onInput = (index) => {
  // Move to the next input field on user input
  if (index < otp.length - 1 && otp[index] !== '') {
    ref[`otpInput${index + 1}`].focus();
  }
};
</script>

<style scoped>
/* Add your styling as needed */
input {
  width: 2em;
  text-align: center;
  margin: 0 0.5em;
}
</style>
