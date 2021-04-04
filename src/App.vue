<template>
    <div class="max-w-xl mx-auto">
        <div class="flex flex-col justify-between p-5 m-5 bg-white border rounded shadow-sm">
            <Header @toggle-add-task="toggleAddTask" title="Task Watcher" :showAddTask="showAddTask" />
            <router-view :showAddTask="showAddTask"></router-view>
            <Footer />
        </div>
    </div>
</template>

<script>
import Header from "./components/Header"
import Footer from "./components/Footer"


export default {
    name: 'App',
    components: {
        Header,
        Footer
    },
    data() {
        return {
            showAddTask: false
        }
    },
    methods: {
        toggleAddTask() {
            this.showAddTask = !this.showAddTask
        }
    }
}
</script>