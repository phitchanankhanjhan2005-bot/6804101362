<script setup>
import { ref } from 'vue'

const name = ref('')
const age = ref(null)
const accept = ref(false)

function onSubmit() {
  console.log('Name:', name.value)
  console.log('Age:', age.value)
  console.log('Accept:', accept.value)
}

function onReset() {
  name.value = ''
  age.value = null
  accept.value = false
}
</script>

<template>
  <q-page class="q-pa-md">
    <q-form
      class="q-gutter-md"
      style="max-width: 600px"
      @submit="onSubmit"
      @reset="onReset"
    >
      <q-input
        v-model="name"
        filled
        label="Your name *"
        hint="Name and surname"
      />

      <q-input
        v-model="age"
        filled
        type="number"
        label="Your age *"
      />

      <q-toggle
        v-model="accept"
        label="I accept the license and terms"
      />

      <div>
        <q-btn
          label="SUBMIT"
          type="submit"
          color="primary"
        />

        <q-btn
          label="RESET"
          type="reset"
          color="primary"
          flat
          class="q-ml-sm"
        />
      </div>
    </q-form>
  </q-page>
</template>
