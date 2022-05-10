<template>
<div>
    <h1> {{concertName}} </h1>
    <h4> {{performerName}} </h4>
</div>
</template>

<script>

export default{
    name: 'Header',
    props:{
        concertName: String,
        performerName:String
    }
}

</script>

<style scoped>

div{
    text-align: center;
}

</style>