<script>
const API_URL = "https://jsonplaceholder.typicode.com/users"
export default {
    data() {
        return {
            data: []
        }
    },
    props: ['id'],
    methods: {
        async fetchData() {
            const res = await fetch(`${API_URL}/${this.id}`)
            this.data = await res.json()
            console.log(this.data);

        },
    },
    mounted() {
        this.fetchData()
    }
}
</script>

<template>
    <div>
        <h1>{{ data.name }}</h1>
        <h3>{{ data.username }}</h3>
        <h5>{{ data.email }}</h5>
    </div>
</template>