<script setup lang="ts">
import { ref, watch } from "vue"
import ChildComponent from "../components/ChildComponent.vue"

const count = ref(0)

watch(count, (newCount) => { console.log("This is the new count" + newCount )});

const message = ref("")
const isHappy = ref(false)

const incrementCounter = () => {
  count.value++
}

const addA = () => {
  message.value += "a"
}

let nextId = 0

const items = ref([
  { id: nextId++, message: "Foo" },
  { id: nextId++, message: "Bar" }
])
</script>
<style>
</style>

<template>
  <h1>You did it!</h1>
  <p>
    Counter: {{ count }}
    Message: {{ message }}
  </p>

  <button v-on:click="incrementCounter">
    Increment Counter
  </button>

  <div>
    <button @click="addA">
      Add an a
    </button>
  </div>

  <div>
    <input v-model="message" />
  </div>

  <div>
    Toggle Happy:
    <input v-model="isHappy" type="checkbox" />
  </div>

  <ChildComponent :items="items"/> 

  <div v-if="isHappy">
    <p>I'm Happy</p>
  </div>

  <div v-else>
    <p>I'm sad</p>
  </div>
</template>