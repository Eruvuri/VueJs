

<template>
    <div >
        <ul><h4>ConcertId: {{concert.id}}</h4></ul>
        <ul><h4>Concert Name: {{concert.concert_name}}</h4></ul>
        <ul><h4> is on: {{getDate(concert.concert_date)}} at {{concert.concert_time}}</h4></ul>
        <ul><h4>Instruments:  {{concert.concert_instruments}}</h4></ul>
        <ul><h4>Ticket Price: {{concert.concert_price}}</h4></ul>
        <ul><h4>performance by: {{concert.performer}}</h4></ul>
        <p :class="concert.tickets_available ? 'green': 'red' ">Availability</p>
        
        
    </div>
</template>


<script>

export default{
    name: 'Concert',
    props:{
        concert: Array
    },
     methods: {
         getDate(datetime) {

            let date = new Date(datetime);

            let dateString = `${date.getMonth() + 1}/${date.getDate()}/${date.getFullYear()  }`

            return dateString
        }

     }
}
</script>

<style scoped>



h4{
    margin: 2px;
}

div{
    width: 90%;
    height: 90%;
    color: white;
    padding: 1em;
    border-radius: 5px;
    border: 0.3em solid  white;
    margin-bottom: 25px auto;
    overflow: auto;
    background: black;
  }
div:hover {
 border: 0.3em solid yellow;
 color: yellow;
}

.red{
background-color: orangered !important;

}
.green{
background-color: rgb(115, 159, 61) ;
}


</style>