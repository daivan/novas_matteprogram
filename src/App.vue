<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'

const guess = ref(0)
const result = ref('')

const props = defineProps({
  firstNumber: {
    type: Number,
    default: 10
  },
  secondNumber: {
    type: Number,
    default: 10
  },
  guess: {
    type: Number,
    default: 0
  },
});

console.log(props.firstNumber)

const Submitting = () => {
  console.log(guess.value)
  if (guess.value == props.firstNumber + props.secondNumber) {
    result.value = "RÄTT"
  } else {
    result.value = "FEL"
  }
}

</script>

<template>

<div>
  <h1>Hej Nova</h1>
  <h1>{{ props.firstNumber }} + {{ props.secondNumber }}</h1>
  <input type="text" v-model="guess" /><button @click="Submitting">Submit</button>
  <h1>{{ result }}</h1>
</div>
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
