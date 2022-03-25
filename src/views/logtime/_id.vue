<script>
const API_URL = "https://jsonplaceholder.typicode.com/users"
export default {
    data() {
        return {
            data: null
        }
    },
    props: ['id'],
    methods: {
        async fetchData() {
            const res = await fetch(`${API_URL}/${this.id}`)
            this.data = await res.json()
            console.log(this.data)

        },
    },
    mounted() {
        this.fetchData()
        console.log(this.id)
    }
}
</script>

<template>
    <div>
        <pre>
         {{ this.data }}
        </pre>
    </div>
</template>