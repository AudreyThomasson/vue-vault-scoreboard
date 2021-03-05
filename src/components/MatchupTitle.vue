<template>
    <h1>
        <span> {{ team1.name}}</span>
        vs
        <span> {{ team2.name}}</span>
    </h1>
  
</template>

<script>
export default {
    props: ["team1", "team2"],
}
</script>

<style>

</style>