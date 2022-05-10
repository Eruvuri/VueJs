<template>
    
     <div class="">
         
        <div v-for="concert in concerts" :key="concert.id" >
                
                <Concert :concert="concert"/>
        </div>

        

     </div>

</template>

<script>

import Concert from "./Concert.vue"
export default{

    name: 'ConcertBox',
    components: {
        Concert
    },
    props: {
        concerts: Array
    }

}

</script>


<style>

.concertbox{

    width : 90%;
    height: 90%;
    background-color: black;
    padding: 1em;
    color: gray;
    display: grid;
    grid-template-columns: repeat(3, minmax(300px, 1fr));
    grid-gap: 15px;
    align-items: stretch;
    font-size: 2vmin;
    margin: 5% 5% 5% 5%;
    
}
</style>