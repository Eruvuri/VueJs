<template>
  <div class="container">
    <!-- #3 must use the component-->
    <Header concertName="Musical Nights" 
      performerName="Lets Rock!!!" />


    <ConcertBox :concerts="concerts"  />




  </div>
</template>
<script>



//import HelloWorld from './components/HelloWorld.vue'
// 1
import Header from './components/Header.vue'
import ConcertBox from './components/ConcertBox.vue'


// data url: http://localhost:5555/books , this might be different for you
export default {
  name: 'App',
  components: {
    // 2 register the component 
    Header,
    ConcertBox
  },

  data(){
    return {
      concerts: []
    }
  },
  methods: {
    // promises

      async fetchConcerts(){
         const res= await fetch('https://nodejs-musicalnights1.herokuapp.com/api')
         const data= await res.json()
          //console.log(data)
         return data
      }

  },

  async created(){
    this.concerts = await this.fetchConcerts()
  }
}
</script>










<style>


@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
}
.container {
  max-width: 400px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 0.3em solid black;
  padding: 30px;
  border-radius: 5px;
}

div{
  margin-bottom: 0.5em;
}



</style>


