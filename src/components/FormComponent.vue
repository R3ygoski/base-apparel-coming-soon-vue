<script setup>
    import {reactive} from 'vue'
    let errorMessage = 'Please provide a valid email'

    const inputData = reactive({
    email: '',
    error: false
    })

    const checkInput = () => {
        if (inputData.email===''){
            inputData.error = true
            errorMessage = 'Email is empty'
        } else if (!inputData.email.includes('@')){
            inputData.error = true
            errorMessage = 'Email needs at least one @'
        } else if (!inputData.email.includes('.com')){
            inputData.error = true
            errorMessage = 'Email needs .com'
        } else {
            inputData.error = false
        }
    }
</script>
<template>
    <form @submit.prevent class="main__form">
      <div class="main__form-wrapper">
        <img class="main__form-icon" :class="{ hidden: !inputData.error }" src="../assets/images/icon-error.svg" alt="Error Icon"/>
        <input type="email" class="main__form-input" :class="{ main__form_input_error: inputData.error }" placeholder="Email Address" v-model="inputData.email"/>
        <button type="submit" class="main__form-btn" @click="checkInput">
          <img src="../assets/images/icon-arrow.svg" alt="Arrow"/>
        </button>
        <p class="main__form-message" :class="{ hidden: !inputData.error }">{{ errorMessage }}</p>
      </div>
    </form>
</template>