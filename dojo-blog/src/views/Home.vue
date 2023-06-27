<template>
  <div class="home">
    hoe
    <p>My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">click me</button>
  </div>
</template>

<script>

export default {
  name: 'Home',
  setup() {
    console.log(this)

    let name = 'Mario'
    let age = 30

    const handleClick = () => {
      console.log('you clicked me')
    }

    return{
       name, //kan også bruke name: name
       age,
       handleClick,
    }
  }
}
</script>
