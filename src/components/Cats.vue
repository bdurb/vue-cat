<template>
  <div class='main'>
    <h1>Lets Get some Cats</h1>
    <button v-on:click="fetchCats">New Cat</button><br/>
    <img :src="cats" />
  </div>
  
</template>

<script>
export default {
  name: "Cats",
  data () {
    return {
      cats: ''
    }
  },
  methods: {
    fetchCats() {
      const url = 'https://aws.random.cat/meow'
      this.$http.get(url)
      .then((res) => {
        this.cats = res.data.file
      })
    }
  }
}
</script>

<style scoped>
.main {
padding-top: 10%;
display: flex;
flex-direction: column;
align-items: center;
}
</style>



