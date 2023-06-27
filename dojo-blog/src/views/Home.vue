<template>
  <div class="home">
    <!-- hoe
    <p ref="p">My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">click me</button>
    <button @click="age++">add 1 to age</button>
    <input type="text" v-model="name"> -->
    <h1>Home</h1>
    <!-- <h2>Refs</h2>
    <p>{{ scholarOne.name }} - {{ scholarOne.age }}</p>
    <button @click="updateScholarOne">Update scholar one</button>
    <h2>Reactive</h2>
    <p>{{ scholarTwo.name }} - {{ scholarTwo.age }}</p>
    <button @click="updateScholarTwo">Update scholar two</button> -->
    <input type="text" v-model="search">
    <p>search term - {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">{{ name }}</div>
  </div>
</template>

<script>
import { computed, ref, watch, watchEffect } from 'vue';

// import { ref, reactive } from 'vue'


export default {
  name: 'Home',
  setup() {
    //console.log(this)

    //const p = ref(null)

    // const name = ref('Mario')
    // const age = ref(30)

    // const handleClick = () => {
    // console.log(p, p.value)
    // p.value.classList.add('test')
    // p.value.textContent = 'hello, scholars'
    // name = 'Luigi'
    //   name.value = 'Luigi'
    //   age.value = 35
    //}

    // const scholarOne = ref({ name: 'Mario', age: 30 })
    // const scholarTwo = reactive({ name: 'Luigi', age: 35 })

    // const updateScholarOne = () => {
    //   scholarOne.value.age = 40
    // }

    // const updateScholarTwo = () => {
    //   scholarTwo.age = 45
    // }

    // const name = computed(() => {
    //   return 'Erwan'
    // })

    const search = ref('')
    const names = ref(['Mario', 'Yoshi P', 'Luigi', 'Toad', 'Bowser', 'Koopa', 'Peach'])

    watch(search, () => {
      console.log('watch function ran')
    })

    watchEffect

    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value))
    })

    return{
      //  name, //kan også bruke name: name
      //  age,
      //  handleClick,
      //p,
      // scholarOne,
      // updateScholarOne,
      // scholarTwo,
      // updateScholarTwo,
      names,
      search,
      matchingNames,
    }
  }
}
</script>
