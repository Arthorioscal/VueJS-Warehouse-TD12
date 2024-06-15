<template>
        <v-simple-table>
            <thead>
                <tr>
                    <th>Code</th>
                    <th>Name</th>
                    <th>Address</th>
                    <th>City</th>
                    <th>Area</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="w in warehouses" :key="w.id">
                    <td>{{ w.code }}</td>
                    <td>{{ w.name }}</td>
                    <td>{{ w.adress }}</td>
                    <td>{{ w.city }}</td>
                    <td>{{ w.area }}</td>
                </tr>
            </tbody>
        </v-simple-table>
</template>

<script>
export default {
    name: 'WarehouseTable',
    props: {
        warehouses:[]
    }
}

</script>