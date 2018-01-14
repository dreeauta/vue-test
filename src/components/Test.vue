<template>
  <div class="test">

    <input type="text" v-model="title"> <br/>

    <h1> {{title}} </h1>
    <p> {{user.firstName}} </p>
    <p v-text="user.firstName"> </p>
    <p v-if="showName"> {{user.firstName}}</p>
    <p v-else> Nobody </p>

    <ul>
      <li v-for="item in items"> {{item.title}} </li>
    </ul>

    <button v-on:click="greet('hello!')"> Say Greeting </button>
    <br/>
    <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit">

    <hr />
    <label> Name </label> <input type="text" v-model="user.firstName">
    <br />
    <label> Species </label> <input type="text" v-model="user.species">
    <h3> {{fullDescription}} </h3>

    <h2> {{msg}}</h2>

  </div>
</template>

<script>
  export default {
    name:'test',
    props: {
      msg: {
        type: String,
        default: 'MSGGG'
      }
    },
    data() {
    return {
      title: 'Test App',
      user: {
        firstName: 'Fiona',
        species: 'dog'
      },
      showName: true,
      items: [
      {title: 'Item1'},
      {title: 'Item2'},
      {title: 'Item3'}
      ]
    }
    },
    methods: {
      greet: function(greet){
        alert(greet)
      },
      pressKey: function(e){
        console.log(e.target.value)
      },
      enterHit: function(){
        console.log('enter')
      }
    },
    computed: {
      fullDescription: function(){
        return this.user.firstName+ ' ' + this.user.species;
      }
    }
  }

</script>

<style scoped>



</style>
