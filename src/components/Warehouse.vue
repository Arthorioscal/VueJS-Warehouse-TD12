<template>
    <div class="card">
        <h3> {{ name }} - {{ code }} </h3>
        <address>
            <strong>Endereço:</strong> {{ adress }}<br>
            <strong>Cidade:</strong> {{ city }}<br>
            <strong>Area:</strong> {{ area }} m²<br>
        </address>
    </div>
</template>

<script>
export default {
    name: 'Warehouse',
    props: {
        id: Number,
        name: String,
        code: String,
        adress: String,
        city: String,
        area: Number,
    }
}
</script>

<style>
    .card{
        border-style: solid;
        border-radius: 25px;
        margin-bottom: 10px;
        width: 30%;
        margin-left: auto;
        margin-right: auto;
    }
</style>