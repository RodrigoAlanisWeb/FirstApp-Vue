<template>
    <h1>
        {{ titulo }}
    </h1>
</template>

<script>
export default {
    name: 'Titulo',
    props: {
        titulo: String
    }
}
</script>

<style scoped>
    h1{
        color: rgb(24, 133, 66);
    }
</style>