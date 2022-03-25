<script>
import { RouterLink, RouterView } from 'vue-router'
const API_URL = "https://jsonplaceholder.typicode.com/users"

export default {
    data() {
        return {
            data: null,
        }
    },
    methods: {
        async fetchData() {
            const res = await fetch(
                API_URL
            )
            this.data = await res.json()
            console.log(this.data)
        },
    },
    mounted() {
        this.fetchData()
    }
}
</script>

<template>
    <div class="container">
        <div class="fs-1 fw-bold mb-4">Logtime Report</div>
        <div class="row">
            <div class="col-6 mb-3" v-for="e in data" :key="e.id">
                <div class="card">
                    <div class="card-header">{{ e.company.name }}</div>
                    <div class="card-body">
                        <h5 class="card-title">{{ e.username }}</h5>
                        <p
                            class="card-text"
                        >{{ e.company.bs }}</p>
                        <router-link to="/" class="btn btn-primary">More</router-link>
                        <!-- <router-link to="/">Test</router-link> -->
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
</style>